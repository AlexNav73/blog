+++
title = "Post 1"
date = 2023-03-16
category = "C#"

[taxonomies]
tags = ["domain model", "generator", "open source"]
+++

## General Overview

`Navitski.Crystalized` is a set of cross-platform libraries which helps to build  your own domain model. They are providing building blocks to implement your own domain model which, from the birds-eye view, will look like on the following diagram:

{% mermaiddiagram() %}
flowchart LR
    subgraph Application
        domainModel[Domain Model] --> shard[Model Shard 1]
        domainModel --> etc[...]
        shard --> col[Collections]
        shard --> rel[Relations]
    end
    subgraph Plug-in
        domainModel --> shard2[Model Shard 2]
    end
{% end %}

The entry point of the model is a class, which inherits `DomainModel` abstract class and contains a collection of model shards. Model shard is a way to split data into pieces by purpose or by business domain boundary. Domain Model collects all model shards 