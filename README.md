# Kibana-D3-plugin

###Writing Kibana plugins

#####Background knowledge:
  * JavaScript development (npm modules; ..)
  * AngularJS (MVC Framework)
  * RequireJS
  
#####Every plugin is a npm module, so at least need: 
* package.json 
* index.js
* a public folder

##### Package ID/name should be globally unique!


### Framework 
├── index.js  
├── package.json  
├── public  
│   ├── kbn_plugin.html  
│   ├── kbn_plugin.js  
│   ├── kbn_plugin.less  
│   ├── kbn_plugin_controller.js  
│   ├── kbn_plugin_params.js  
│   └── lib  
│      　　 └── agg_response.js  

(Could also combine agg_response.js into kbn_plugin_controller.js)

### Data Passing 
* esResponse: Holds the Elasticsearch response for your visualization. 
* vis: Holds information about your visualization and the settings the user chose.

Access data from metrix:  ```$scope.vis.aggs.bySchemaName['your_metrix_name'][0];```

Access data from buckets: ```$scope.vis.aggs.bySchemaName['your_bucket_name'][0].id;```

### Set Schema 
* Metrics aggregations(aggFilter): avg, cardinality, count, max, median, min, percentile_ranks, percentiles, std_dev, sum

* Bucket aggregations(aggFilter): date_histogram, date_range, filters, geohash_grid, histogram, ip_range, range, significant_terms, terms

### Resources
[Github/JuanCarniglia](https://github.com/JuanCarniglia/kbn_boxplot_violin_vis/tree/master/public)

[Writing Kibana 4 Plugins] (https://www.timroes.de/2015/12/02/writing-kibana-4-plugins-basics/)

[Kibana Plugin Yeoman Generator] (https://www.npmjs.com/package/generator-kibana-plugin)

[{{more}} Kibana4]  (http://www.slideshare.net/chenryn/more-kibana4)

[Data visualization with Elasticsearch aggregations and D3](https://www.elastic.co/blog/data-visualization-elasticsearch-aggregations)

[Creating Custom Kibana Visualizations: A How-To Guide] (http://logz.io/blog/kibana-visualizations/)

[Kibana4 可视化插件开发](https://github.com/chenryn/ELKstack-guide-cn/blob/master/kibana/v4/plugin/vis-develop.md)


