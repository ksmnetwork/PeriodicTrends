# PeriodicTrends
Monitoring on the current active nodes from 1000 Validators program at KUSAMA NETWORK by "Offline Event and Faults". Datasource JSON plugin for Grafana with endpoint https://kusama.w3f.community/candidates

![Dashboard](https://grafana.com/api/dashboards/16178/images/12069/image)

Dashboard JSON:
```
{
  "__inputs": [
    {
      "name": "DS_1KV_CANDIDATES",
      "label": "1KV Candidates",
      "description": "Data taken from: https://kusama.w3f.community/candidates",
      "type": "datasource",
      "pluginId": "marcusolsson-json-datasource",
      "pluginName": "JSON API"
    }
  ],
  "__elements": [],
  "__requires": [
    {
      "type": "grafana",
      "id": "grafana",
      "name": "Grafana",
      "version": "8.5.0"
    },
    {
      "type": "datasource",
      "id": "marcusolsson-json-datasource",
      "name": "JSON API",
      "version": "1.2.1"
    },
    {
      "type": "panel",
      "id": "stat",
      "name": "Stat",
      "version": ""
    }
  ],
  "annotations": {
    "list": [
      {
        "builtIn": 1,
        "datasource": {
          "type": "grafana",
          "uid": "-- Grafana --"
        },
        "enable": true,
        "hide": true,
        "iconColor": "rgba(0, 211, 255, 1)",
        "name": "Annotations & Alerts",
        "target": {
          "limit": 100,
          "matchAny": false,
          "tags": [],
          "type": "dashboard"
        },
        "type": "dashboard"
      }
    ]
  },
  "description": "Monitoring on the current active validators at KUSAMA NETWORK",
  "editable": true,
  "fiscalYearStartMonth": 0,
  "graphTooltip": 0,
  "id": null,
  "links": [],
  "liveNow": false,
  "panels": [
    {
      "datasource": {
        "type": "marcusolsson-json-datasource",
        "uid": "${DS_1KV_CANDIDATES}"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "super-light-green",
                "value": null
              },
              {
                "color": "green",
                "value": 1
              },
              {
                "color": "super-light-yellow",
                "value": 2
              },
              {
                "color": "yellow",
                "value": 3
              },
              {
                "color": "dark-yellow",
                "value": 4
              },
              {
                "color": "orange",
                "value": 5
              },
              {
                "color": "dark-orange",
                "value": 6
              },
              {
                "color": "light-red",
                "value": 7
              },
              {
                "color": "red",
                "value": 8
              },
              {
                "color": "dark-red",
                "value": 9
              },
              {
                "color": "#79000e",
                "value": 10
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 15,
        "w": 24,
        "x": 0,
        "y": 0
      },
      "id": 2,
      "interval": "1m",
      "options": {
        "colorMode": "background",
        "graphMode": "area",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "/^faults$/",
          "limit": 1000,
          "values": true
        },
        "textMode": "value_and_name"
      },
      "pluginVersion": "8.5.0",
      "targets": [
        {
          "cacheDurationSeconds": 300,
          "datasource": {
            "type": "marcusolsson-json-datasource",
            "uid": "${DS_1KV_CANDIDATES}"
          },
          "fields": [
            {
              "jsonPath": "$.[?(@.active == true)].name",
              "name": ""
            },
            {
              "jsonPath": "$.[?(@.active == true)].faults",
              "name": ""
            },
            {
              "jsonPath": "$.[?(@.active == true)].offlineAccumulated",
              "name": ""
            }
          ],
          "hide": false,
          "method": "GET",
          "queryParams": "",
          "refId": "A",
          "urlPath": ""
        }
      ],
      "title": "Validators with Fauts",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "marcusolsson-json-datasource",
        "uid": "${DS_1KV_CANDIDATES}"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "super-light-green",
                "value": null
              },
              {
                "color": "green",
                "value": 1
              },
              {
                "color": "super-light-yellow",
                "value": 2
              },
              {
                "color": "yellow",
                "value": 3
              },
              {
                "color": "dark-yellow",
                "value": 4
              },
              {
                "color": "orange",
                "value": 5
              },
              {
                "color": "dark-orange",
                "value": 6
              },
              {
                "color": "light-red",
                "value": 7
              },
              {
                "color": "red",
                "value": 8
              },
              {
                "color": "dark-red",
                "value": 9
              },
              {
                "color": "#79000e",
                "value": 10
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 12,
        "w": 24,
        "x": 0,
        "y": 15
      },
      "id": 3,
      "interval": "1m",
      "options": {
        "colorMode": "background",
        "graphMode": "area",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "/^offlineAccumulated$/",
          "limit": 1000,
          "values": true
        },
        "textMode": "value_and_name"
      },
      "pluginVersion": "8.5.0",
      "targets": [
        {
          "cacheDurationSeconds": 300,
          "datasource": {
            "type": "marcusolsson-json-datasource",
            "uid": "${DS_1KV_CANDIDATES}"
          },
          "fields": [
            {
              "jsonPath": "$.[?(@.active == true)].name",
              "name": ""
            },
            {
              "jsonPath": "$.[?(@.active == true)].faults",
              "name": ""
            },
            {
              "jsonPath": "$.[?(@.active == true)].offlineAccumulated",
              "name": ""
            }
          ],
          "hide": false,
          "method": "GET",
          "queryParams": "",
          "refId": "A",
          "urlPath": ""
        }
      ],
      "title": "Validators with Offline Event",
      "type": "stat"
    }
  ],
  "refresh": "",
  "schemaVersion": 36,
  "style": "dark",
  "tags": [
    "ksm.network",
    "kusama",
    "polkadot",
    "substrate"
  ],
  "templating": {
    "list": []
  },
  "time": {
    "from": "now-6h",
    "to": "now"
  },
  "timepicker": {},
  "timezone": "",
  "title": "1000 Validators Periodic trends",
  "uid": "E2ygL_Q7k",
  "version": 5,
  "weekStart": "",
  "gnetId": 16178
}
```
