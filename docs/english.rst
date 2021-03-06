.. include:: global.rst

.. meta::
   :DC.creator: Gouvernement du Québec
   :DC.language: en

--------------------
English
--------------------

|igo-logo|

* Installation: `<https://github.com/infra-geo-ouverte/igo2#installation-en>`_
* Demo: `<https://infra-geo-ouverte.github.io/igo2/>`_
* Tests: `<https://github.com/infra-geo-ouverte/igo2#tests-en>`_
* Docker: `<https://github.com/infra-geo-ouverte/igo2#docker-en>`_
* Overview of the project: `<https://overv.io/infra-geo-ouverte/igo2/>`_
* GitHub repository: `<https://github.com/infra-geo-ouverte/igo2/>`_


Latest update: |date| (|time| UTC)

|CC|


JSON-EN
=================

This section include all configuration possible in the Web |igo2|_ Mapping application. 
With this JSON conguration file, it is possible to build your own context, tools and layers related to each uses.


Parameters related to JSON : 

* /src/contexts/

{
  "map":{
    "view":{
      "projection":"EPSG:3857",
      "center":[
        -72,
        52
      ],
      "zoom":6
    }
  },
  "layers":[
    {
      "name":"name_title_alias_wmts",
      "type":"wmts",
      "source":{
        "url":"http://geoegl.msp.gouv.qc.ca/cgi-wms/mapcache.fcgi/wmts",
        "matrixSet":"EPSG_3857",
        "format":"image/jpeg",
        "layer":"layername_wmts"
      }
    },
    {
      "name":"name_title_alias__xyz_tms",
      "type":"xyz",
      "source":{
        "url":"https://geoegl.msp.gouv.qc.ca/cgi-wms/mapcache.fcgi/tms/1.0.0/carte_gouv_qc_ro@EPSG_3857/{z}/{x}/{-y}.png"
      }
    },
    {
      "name":"name_title_alias_wms",
      "type":"wms",
      "source":{
        "url":"http://geoegl.msp.gouv.qc.ca/cgi-wms/igo_gouvouvert.fcgi?",
        "params":{
          "LAYERS":"layername_wms",
          "VERSION":"1.1.1"
        }
      }
    },
    {
      "title": "name_title_alias_wms_time",
      "type": "wms",
      "source": {
        "url": "http://geoegl.msp.gouv.qc.ca/cgi-wms/igo_gouvouvert.fcgi",
        "params": {
          "layers": "layername_wms_time",
          "version": "1.3.0"
        }
      },
      "timeFilter": {
        "min": "2017-01-01",
        "max": "2018-01-01",
        "range": true,
        "type": "datetime"
      }
     },
    {
      "name" : "WFS",
      "title": "Bassin (WFS)",
      "type" : "wfs",
      "source":{
        "url" : "http://geoegl.msp.gouv.qc.ca/cgi-wms/adnInternetV2.fcgi?service=WFS&version=1.1.0&request=GetFeature&typename=adn_bassin_n1_simplify_500&srsname=EPSG:3857"
      },
      "style" : {
        "Stroke" : {
            "color" : "rgba(140, 140, 255, 1.0)",
            "width" : 3
        }
      },
      "version" : "1.3.0"
    },
    {
      "title":"LayerfromCapabilities",
      "type":"wms",
      "optionsFromCapabilities":true,
      "alias":"US-States",
      "source":{
        "url":"http://demo.boundlessgeo.com/geoserver/wms",
        "params":{
          "layers":"topp:states",
          "version":"1.3.0"
        },
        "serverType":"geoserver"
      }
    }
  ],
  "toolbar":[
    "search",
    "context",
    "mapEditor",
    "layers",
    "directions",
    "historicalAnalysis",
    "print",
    "measure"
  ],
  "tools":[
    {
      "name":"context",
      "title":"Contexts",
      "icon":"local_offer"
    },
    {
      "name":"search"
    },
    {
      "name":"mapEditor"
    },
    {
      "name":"add_layers",
      "title":"Add Layers",
      "icon":"add_location"
    },
    {
      "name":"directions",
      "title":"Directions",
      "icon":"directions"
    },
    {
      "name":"historical_analysis",
      "title":"Historical Analysis",
      "icon":"history"
    },
    {
      "name":"print",
      "title":"Print",
      "icon":"local_printshop"
    },
    {
      "name":"measure",
      "title":"Measure",
      "icon":"straighten"
    }
  ]
}

More information available here: http://igouverte.org/english/.


----------

.. toctree::
   :maxdepth: 2
   
   config_json_en


List of individual code `contributeurs`_.       


.. note::
   This documentation is under construction.
