# DIO - Inteligencia de Documentos e Mineração de Conhecimento no Azure
Azure Cognitive Search: Utilizando AI Search para indexação e consulta de Dados

## 🔎 O que é o Azure AI Search?	

>O Azure AI Search fornece recuperação de informações seguras em escala sobre o conteúdo de propriedade do usuário em aplicativos de pesquisa tradicionais e de conversa.

<sub>Fonte: <https://learn.microsoft.com/pt-br/azure/search/search-what-is-azure-search></sub>


## Criação do recurso do Azure AI Search
Entre no portal do Azure.

Clique no botão `+ Create a resource`, pesquise **Azure AI Search** e crie um recurso Azure AI Search com as seguintes configurações:

- *Subscription*: Sua assinatura do Azure.
- *Resource group*: Selecione ou crie um grupo de recursos com um nome exclusivo.
- *Service name*: Um nome exclusivo em letra minúscula.
- *Location*: Escolha qualquer região disponível.
- *Pricing tier*: Básico
Clique em `Review + create` e depois de ver a resposta **Validation Success**, clique em `Create`.

Após a conclusão da implantação, clique em `Go to resource`.

## Crie um recurso de serviços de IA do Azure
Retorne à página inicial do portal do Azure. Clique em ```＋Create a resource``` e pesquise por **Azure AI services**. Clique em criar um plano de **Azure AI services**. Configure-o da seguinte maneira:
- *Subscription*: Sua assinatura do Azure.
- *Resource group*: O mesmo grupo de recursos que seu recurso do Azure AI Search.
- *Region*: O mesmo local do recurso do Azure AI Search.
- *Name*: Um nome exclusivo.
- *Pricing tier*: Padrão S0
- *Marcar a caixa* **By checking this box I acknowledge that I have read and understood all the terms below**
Clique em ```Review + create```. Depois de ver a resposta **Validation Passed**, clique em ```Create```.


## Crie uma conta de armazenamento
Retorne à página inicial do portal do Azure e clique em **+ Create a resource**.

Procure por **Storage account** e crie um novo com as seguintes configurações:
- *Subscription*: Sua assinatura do Azure.
- *Resource group*: O mesmo grupo de recursos que os recursos do Azure AI Search e dos serviços Azure AI.
- *Storage account name*: Um nome exclusivo em letras minúsculas.
- *Location*: Escolha qualquer localização disponível.
- *Performance*: Padrão.
- *Redundancy*: Armazenamento localmente redundante (LRS).
Clique em `Review + create` e em ```Create```.

Na conta de Armazenamento do Azure criada, clique em ```Configuration```.
Habilite a configuração **Allow Blob anonymous** e clique em ```Save```.

## Carregar documentos para o armazenamento do Azure
No painel do menu esquerdo, clique em ```Containers```.

Clique em ```+ Container```. Insira as seguintes configurações e clique em ```Create```:
- *Name*: coffee-reviews
- *Public access level*: Container (acesso de leitura anônimo para containers e blobs)
- *Advanced*: sem alterações.
Em uma nova guia do navegador, baixe as avaliações de café compactadas em ```https://aka.ms/mslearn-coffee-reviews```, e extraia os arquivos para a pasta de reviews.

No portal do Azure, selecione o contêiner **coffee-reviews**. No contêiner, clique em ```Upload```.

No painel **Upload blob**, clique em ```Select a file```.

Na janela do Explorer, selecione todos os arquivos na pasta de avaliações, clique em ```Open``` e, em seguida, ```Upload```.

Após o upload concluir, feche o painel **Upload blob**.

## Indexar os documentos
No portal do Azure, navegue até o recurso Azure AI Search. Na página **Overview**, clique em ```Import data```.

Na página **Connect to your data**, na lista **Data Source**, clique em ```Azure Blob Storage``` e preencha da seguinte forma:
- *Data Source*: Azure Blob Storage
- *Data source name*: coffee-customer-data
- *Data to extract*: Content and metadata
- *Parsing mode*: Padrão
- *Connection string*: Clique em **Choose an existing connection**. Selecione sua conta de armazenamento, selecione o contêiner *coffee-reviews* e clique em ```Select```.
- *Managed identity authentication*: Nenhuma
- *Container name*: essa configuração é preenchida automaticamente.
- *Blob folder*: Deixe em branco.
- *Description*: Reviews for Fourth Coffee shops.

Clique em ```Next: Add cognitive skills (Optional)```.

Selecione o recurso de serviços Azure AI e na seção **Add enrichments**:
- Altere o nome da qualificação para **coffee-skillset**.
- Marque a caixa de seleção **Enable OCR and merge all text into merged_content field**.
- O campo **Source data field** deve estar configurado como **merged_content**.
- Altere o nível de granularidade de enriquecimento para **Pages (5000 character chunks)**.
- Não selecione *Enable incremental enrichment*

Selecione os seguintes campos:
Habilidade Cognitiva	Nome do campo
Extraia nomes de locais	 	Localizações
Extraia frases-chave	 	frases chave
Detectar sentimento	 	sentimento
Gerar tags de imagens	 	imagemTags
Gere legendas de imagens	 	legenda da imagem

Em **Save enrichments to a knowledge store**, selecione as opções destacadas na imagem abaixo:
Projeções de imagem
Documentos
Páginas
Frases chave
Entidades
Detalhes da imagem
Referências de imagem

Se aparecer um aviso solicitando uma **Storage Account Connection String**, clique em **Select Choose an existing connection**. 

Escolha a conta de armazenamento criada anteriormente.
Clique em **+ Container** para criar um novo contêiner chamado **knowledge-store** com o nível de privacidade definido como **Private**, e clique em **Create**.

Selecione o contêiner knowledge-store, e clique em `Select`.

Em **Azure blob projections** selecione **Documento**.

Clique em ```Next: Customize target index``` e no campo **Index name** preencha **coffee-index**.

Certifique-se de que a chave esteja configurada como **metadata_storage_path**. Deixe **Suggester name** em branco e **Search mode** preenchido automaticamente.


Revise as configurações padrão dos campos de índice. Selecione filterable para todos os campos que já estão selecionados por padrão.



Clique em ```Next: Create an indexer```.

Altere o nome do indexador para **coffee-indexer**.

Deixe a programação definida como **Once**.

Expanda as opções avançadas. Certifique-se de que a opção **Base-64 Encode Keys** esteja selecionada, pois as chaves de codificação podem tornar o índice mais eficiente.

Clique em ```Submit```. 

Volte à página de recursos do Azure AI Search. Em **Search Management**, clique em ```Indexers``` e **coffee-indexer**. Espere até que o status indique sucesso ou clique em ```Refresh```.

## Consultar o índice
Na página **Overview** do Search service, clique em ```Search explorer```.

Abaixo do índice selecionado, altere a visualização para **JSON view**.

No campo do editor de consultas JSON, copie e cole:
```
{
    "search": "*",
    "count": true
}
```

Clique em ```Search```. A consulta retorna uma contagem de todos os documentos no campo **@odata.count** e um documento JSON contendo os resultados da pesquisa.

No campo do editor de consultas JSON , copie e cole para filtrar por localização:
```
{
 "search": "locations:'Illinois'",
 "count": true
}
```

Clique em ```Search```. A consulta irá filtrar 3 revisões com localização em Illinois no campo **@odata.count**.

Para filtrar por sentimento, no campo do editor de consultas JSON , copie e cole:
```
{
 "search": "sentiment:'positive'",
 "count": true
}
```

Clique em ```Search```. A consulta irá filtrar 7 revisões com sentimento positivo no campo **@odata.count**.

Veja como os resultados são classificados por @search.score. Esta é a pontuação atribuída pelo mecanismo de pesquisa para mostrar o quão próximos os resultados correspondem à consulta fornecida.

## Revise o armazenamento de conhecimento
No portal do Azure, navegue de volta para a sua conta de armazenamento do Azure.

No menu esquerdo, clique em ```Containers```. Selecione o contêiner **knowledge-store**.

Selecione qualquer um dos itens e clique no arquivo **objectprojection.json**.

Clique em ```Edit``` para ver o JSON produzido para um dos documentos do seu armazenamento de dados do Azure.

Retornando em **Containers**, clique no contêiner **coffee-skillset-image-projection**. Selecione qualquer um dos itens e qualquer um dos arquivos *.jpg*. Clique em ```Edit``` para ver a imagem armazenada no documento.

Selecione a localização atual do blob de armazenamento no canto superior esquerdo da tela para retornar à conta de armazenamento **Containers**.

Clique em **Storage browser** no painel esquerdo e selecione **Tables**. Há uma tabela para cada entidade no índice. Selecione a tabela **coffeeSkillsetKeyPhrases** e observe as frases-chave que o armazenamento de conhecimento conseguiu capturar do conteúdo das avaliações.


## Links utilizados

- <https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html>

- (https://portal.azure.com)

- (https://learn.microsoft.com/pt-br/azure/search/search-what-is-azure-search)


