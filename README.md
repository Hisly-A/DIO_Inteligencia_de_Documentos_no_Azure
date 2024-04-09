# DIO - Inteligencia de Documentos e Mineração de Conhecimento no Azure
Azure Cognitive Search: Utilizando AI Search para indexação e consulta de Dados

## 🔎 O que é o Azure AI Search?	

>O Azure AI Search fornece recuperação de informações seguras em escala sobre o conteúdo de propriedade do usuário em aplicativos de pesquisa tradicionais e de conversa.

<sub>Fonte: <https://learn.microsoft.com/pt-br/azure/search/search-what-is-azure-search></sub>


## Criação do recurso do Azure AI Search
Entre no portal do [`Azure`](https://portal.azure.com).

Clique no botão `+ Create a resource`, pesquise **Azure AI Search**.

<div align="center">
    <img width="700" title="MC01" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC01.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC02" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC02.PNG"/>
</div>
<br>

Crie um recurso Azure AI Search com as seguintes configurações:

- *Subscription*: Sua assinatura do Azure.
- *Resource group*: Selecione ou crie um grupo de recursos com um nome exclusivo.
- *Service name*: Um nome exclusivo em letra minúscula.
- *Location*: Escolha qualquer região disponível.
- *Pricing tier*: Básico

<div align="center">
    <img width="700" title="MC03" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC03.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC04" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC04.PNG"/>
</div>
<br>

Clique em `Review + create` e depois de ver a resposta **Validation Success**, clique em `Create`.

<div align="center">
    <img width="700" title="MC05" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC05.PNG"/>
</div>
<br>

Após a conclusão da implantação, clique em `Go to resource`.

<div align="center">
    <img width="700" title="MC06" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC06.PNG"/>
</div>
<br>


## Crie um recurso de serviços de IA do Azure
Retorne à página inicial do portal do [`Azure`](https://portal.azure.com). Clique em `＋Create a resource` e pesquise por **Azure AI services**. Clique em criar um plano de **Azure AI services**. 

<div align="center">
    <img width="700" title="MC07" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC07.PNG"/>
</div>
<br>
<div align="center">
    <img width="500" title="MC08" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC08.PNG"/>
</div>
<br>

Configure-o da seguinte maneira:
- *Subscription*: Sua assinatura do Azure.
- *Resource group*: O mesmo grupo de recursos que seu recurso do Azure AI Search.
- *Region*: O mesmo local do recurso do Azure AI Search.
- *Name*: Um nome exclusivo.
- *Pricing tier*: Padrão S0
- *Marcar a caixa* **By checking this box I acknowledge that I have read and understood all the terms below**

<div align="center">
    <img width="700" title="MC09" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC09.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC10" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC10.PNG"/>
</div>
<br>

Clique em `Review + create`. Depois de ver a resposta **Validation Passed**, clique em ```Create```.

<div align="center">
    <img width="700" title="MC11" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC11.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC12" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC12.PNG"/>
</div>
<br>


## Crie uma conta de armazenamento
Retorne à página inicial do portal do [`Azure`](https://portal.azure.com), clique em `+ Create a resource` e procure por **Storage account**.

<div align="center">
    <img width="700" title="MC13" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC13.PNG"/>
</div>
<br>
<div align="center">
    <img width="500" title="MC14" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC14.PNG"/>
</div>
<br>

Crie um novo com as seguintes configurações:
- *Subscription*: Sua assinatura do Azure.
- *Resource group*: O mesmo grupo de recursos que os recursos do Azure AI Search e dos serviços Azure AI.
- *Storage account name*: Um nome exclusivo em letras minúsculas.
- *Location*: Escolha qualquer localização disponível.
- *Performance*: Padrão.
- *Redundancy*: Armazenamento localmente redundante (LRS).

<div align="center">
    <img width="700" title="MC15" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC15.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC16" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC16.PNG"/>
</div>
<br>

Clique em `Review + create` e em `Create`.

<div align="center">
    <img width="700" title="MC17" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC17.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC18" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC18.PNG"/>
</div>
<br>

Na conta de Armazenamento do Azure criada, clique em `Configuration`, habilite a configuração **Allow Blob anonymous** e clique em `Save`.

<div align="center">
    <img width="700" title="MC19" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC19.PNG"/>
</div>
<br>


## Carregar documentos para o armazenamento do Azure
No painel do menu esquerdo, clique em **Containers**.

Clique em `+ Container`. Insira as seguintes configurações e clique em `Create`:
- *Name*: coffee-reviews
- *Public access level*: Container (acesso de leitura anônimo para containers e blobs)
- *Advanced*: sem alterações.

<div align="center">
    <img width="700" title="MC20" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC20.PNG"/>
</div>
<br>

Em uma nova guia do navegador, baixe as avaliações de café compactadas em ```https://aka.ms/mslearn-coffee-reviews```, e extraia os arquivos para a pasta de reviews.

No portal do [`Azure`](https://portal.azure.com), selecione o contêiner **coffee-reviews**. No contêiner, clique em `Upload`.

<div align="center">
    <img width="700" title="MC21" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC21.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC22" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC22.PNG"/>
</div>
<br>

No painel **Upload blob**, clique em `Select a file`.

Na janela do Explorer, selecione todos os arquivos na pasta de avaliações, clique em `Open` e, em seguida, `Upload`.

Após o upload concluir, feche o painel **Upload blob**.

<div align="center">
    <img width="700" title="MC23" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC23.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC24" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC24.PNG"/>
</div>
<br>


## Indexar os documentos
No portal do [`Azure`](https://portal.azure.com), navegue até o recurso **Azure AI Search**. Na página **Overview**, clique em `Import data`.

<div align="center">
    <img width="700" title="MC25" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC25.PNG"/>
</div>
<br>

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

<div align="center">
    <img width="700" title="MC26" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC26.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC27" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC27.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC28" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC28.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC29" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC29.PNG"/>
</div>
<br>

Clique em ```Next: Add cognitive skills (Optional)```.

<div align="center">
    <img width="700" title="MC30" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC30.PNG"/>
</div>
<br>

Selecione o recurso de serviços Azure AI e na seção **Add enrichments**:
- Altere o nome da qualificação para **coffee-skillset**.
- Marque a caixa de seleção **Enable OCR and merge all text into merged_content field**.
- O campo **Source data field** deve estar configurado como **merged_content**.
- Altere o nível de granularidade de enriquecimento para **Pages (5000 character chunks)**.
- Não selecione *Enable incremental enrichment*

<div align="center">
    <img width="700" title="MC31" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC31.PNG"/>
</div>
<br>

Selecione os seguintes campos:

<div align="center">
    <img width="700" title="MC32" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC32.PNG"/>
</div>
<br>

Em **Save enrichments to a knowledge store**, selecione as opções destacadas na imagem abaixo:

<div align="center">
    <img width="700" title="MC34" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC34.PNG"/>
</div>
<br>

Se aparecer um aviso solicitando uma **Storage Account Connection String**, clique em **Choose an existing connection**. 

<div align="center">
    <img width="700" title="MC49" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC49.PNG"/>
</div>
<br>

Escolha a conta de armazenamento criada anteriormente.

<div align="center">
    <img width="700" title="MC50" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC50.PNG"/>
</div>
<br>

Clique em **+ Container** para criar um novo contêiner chamado **knowledge-store** com o nível de privacidade definido como **Private**, e clique em **Create**.

<div align="center">
    <img width="700" title="MC51" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC51.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC52" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC52.PNG"/>
</div>
<br>

Selecione o contêiner **knowledge-store**, e clique em `Select`.

<div align="center">
    <img width="700" title="MC53" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC53.PNG"/>
</div>
<br>

Em **Azure blob projections** selecione **Documento** e clique em `Next: Customize target index` :

<div align="center">
    <img width="700" title="MC54" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC54.PNG"/>
</div>
<br>

No campo **Index name** preencha **coffee-index**.

Certifique-se de que a chave esteja configurada como **metadata_storage_path**. Deixe **Suggester name** em branco e **Search mode** preenchido automaticamente.

<div align="center">
    <img width="700" title="MC37" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC37.PNG"/>
</div>
<br>

Selecione **filterable** para todos os campos que já estão selecionados por padrão e após clique em `Next: Create an indexer`.

<div align="center">
    <img width="700" title="MC38" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC38.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC39" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC39.PNG"/>
</div>
<br>

Altere o nome do indexador para **coffee-indexer**.

Deixe a programação definida como **Once**.

Expanda as opções avançadas. Certifique-se de que a opção **Base-64 Encode Keys** esteja selecionada, pois as chaves de codificação podem tornar o índice mais eficiente. Clique em ```Submit```. 

<div align="center">
    <img width="700" title="MC40" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC40.PNG"/>
</div>
<br>

Volte à página de recursos do **Azure AI Search**. Em **Search Management**, clique em ```Indexers``` e **coffee-indexer**. Espere até que o status indique sucesso ou clique em ```Refresh```.

<div align="center">
    <img width="700" title="MC41" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC41.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC42" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC42.PNG"/>
</div>
<br>


## Consultar o índice
Na página **Overview** do Search service, clique em ```Search explorer```.

<div align="center">
    <img width="700" title="MC43" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC43.PNG"/>
</div>
<br>

Abaixo do índice selecionado, altere a visualização para **JSON view**.

<div align="center">
    <img width="700" title="MC44" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC44.PNG"/>
</div>
<br>

No campo do editor de consultas JSON, copie e cole:
```
{
    "search": "*",
    "count": true
}
```

Clique em ```Search```. A consulta retorna uma contagem de todos os documentos no campo *@odata.count* e um documento [`JSON`](https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/Todos_os_documentos.json) contendo os resultados da pesquisa.

<div align="center">
    <img width="700" title="MC45" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC45.PNG"/>
</div>
<br>

No campo do editor de consultas JSON , copie e cole para filtrar por localização:
```
{
 "search": "locations:'Illinois'",
 "count": true
}
```

Clique em ```Search```. A consulta irá filtrar 3 revisões com localização em Illinois no campo *@odata.count*.

<div align="center">
    <img width="700" title="MC46" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC46.PNG"/>
</div>
<br>

Para filtrar por sentimento, no campo do editor de consultas JSON , copie e cole:
```
{
 "search": "sentiment:'positive'",
 "count": true
}
```

Clique em ```Search```. A consulta irá filtrar 7 revisões com sentimento positivo no campo *@odata.count*.

<div align="center">
    <img width="700" title="MC47" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC47.PNG"/>
</div>
<br>

Veja como os resultados são classificados por *@search.score*. Esta é a pontuação atribuída pelo mecanismo de pesquisa para mostrar o quão próximos os resultados correspondem à consulta fornecida.

<div align="center">
    <img width="700" title="MC48" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC48.PNG"/>
</div>
<br>


## Revise o armazenamento de conhecimento
No portal do [`Azure`](https://portal.azure.com), navegue de volta para a sua conta de armazenamento do Azure.

No menu esquerdo, clique em ```Containers```. Selecione o contêiner **knowledge-store**.

<div align="center">
    <img width="700" title="MC55" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC55.PNG"/>
</div>
<br>

Selecione qualquer um dos itens e clique no arquivo **objectprojection.json**.

<div align="center">
    <img width="700" title="MC56" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC56.PNG"/>
</div>
<br>

Clique em `Edit` para ver o JSON produzido para um dos documentos do seu armazenamento de dados do Azure.

<div align="center">
    <img width="700" title="MC57" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC57.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC58" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC58.PNG"/>
</div>
<br>

Retornando em **Containers**, clique no contêiner **coffee-skillset-image-projection**. Selecione qualquer um dos itens e qualquer um dos arquivos *.jpg*. Clique em ```Edit``` para ver a imagem armazenada no documento.

<div align="center">
    <img width="700" title="MC59" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC59.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC60" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC60.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC61" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC61.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC62" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC62.PNG"/>
</div>
<br>

Retorne à conta de armazenamento **Containers** e clique em **Storage browser** no painel esquerdo e clique em **Tables**. Há uma tabela para cada entidade no índice. Selecione a tabela **coffeeSkillsetKeyPhrases** e observe as frases-chave que o armazenamento de conhecimento conseguiu capturar do conteúdo das avaliações.

<div align="center">
    <img width="700" title="MC63" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC63.PNG"/>
</div>
<br>
<div align="center">
    <img width="700" title="MC64" src="https://github.com/Hisly-A/DIO_Inteligencia_de_Documentos_no_Azure/blob/main/outputs/MC64.PNG"/>
</div>
<br>


## Links utilizados

- https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html

- https://portal.azure.com

- https://learn.microsoft.com/pt-br/azure/search/search-what-is-azure-search
