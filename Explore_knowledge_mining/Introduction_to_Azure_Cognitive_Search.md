# Introduction to Azure Cognitive Search

## Introduction

- Solutions that involve extracting information from large volumes of often unstructured data
- **Azure Cognitive Search** is a cloud search service that has tools for building user-managed indexes and can be used for internal use only or to enable searchable content on public-facing internet assets
- Can utilize the built-in AI capabilities of Azure Cognitive Services such as image processing, content extraction and natural language processing to perform knowledge mining of documents

## What is Azure Cognitive Search?

- Platform as a Service (PaaS) solution where Microsoft manages infrastructure and availability, allowing your organization to benefit without the need to purchase or manage dedicated hardware resources

### Azure Cognitive Search features

- **Data from any source**: accepts data from any source provided in JSON format, with auto crawling support for selected data sources in Azure
- **Full text search and analysis**: supports both simple query and full Lucene query syntax
- **AI powered search**: AI capabilities built in for image and text analysis from raw content
- **Multi-lingual**: linguistic analysis for 56 languages to intelligently handle phonetic matching or language-specific linguistics (also used by Bing and Office)
- **Geo-enabled**: supports geo-search filtering based on proximity to a physical location
- **Configurable user experience**: several features to improve the user experience inlcuding autocomplete, autosuggest, pagination and hit highlighting

## Identify elements of a search solution

- Typically starts with a data source that contains the data artifacts you want to search
- Regardless of where your data originates, if you can provide it as a JSON document, the search engine can index it
- If your data resides in supported data source, you can use an indexer to automate data ingestion, including JSON serialization of source data in native formats
- Fields containing your content are persisted in an index, which can be searched by client applications and are used for searching, filtering, and sorting to generate a set of results that can be displayed or otherwise used by the client application

## Use a skillset to define an enrichment pipeline

