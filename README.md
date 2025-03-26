# DIAMOND SHOVEL-WORKBENCH

shovel-workbench是基于[diamond-shovel](https://github.com/diamond-shovel/diamond-shovel)框架制作的外围WEB-UI项目

它能使用户快速的按场景部署任务流，从而稳健建设的私有化资产管理体系。

## WIKI

WIKI请见[diamond-shovel-wiki](https://diamond-shovel.github.io/shovel-wiki/)

## Project Structure

```mermaid
graph TB
    subgraph Shovel Plugins
        shovel-plugin1[shovel-plugin-1]
        shovel-plugin2[shovel-plugin-2]
        shovel-pluginN[shovel-plugin-N]
    end

    subgraph Shovel Cores
        shovel-core1[shovel-core-1]
        shovel-core2[shovel-core-2]
        shovel-coreN[shovel-core-N]
    end

    subgraph Middleware
        shovel-db[shovel-db]
        other-middleware[其他中间件]
    end

    scheduler[scheduler]
    intermediate[shovel-intermediate-layer]
    frontend[shovel-frontend]
    nginx[nginx]
    workbench[shovel-workbench]

    shovel-plugin1 --> shovel-core1
    shovel-plugin2 --> shovel-core1
    shovel-pluginN --> shovel-coreN

    shovel-core1 --> scheduler
    shovel-core2 --> scheduler
    shovel-coreN --> scheduler

    scheduler --> intermediate
    shovel-db --> intermediate
    other-middleware --> intermediate

    intermediate --> nginx
    frontend --> nginx

    nginx --> workbench
```


