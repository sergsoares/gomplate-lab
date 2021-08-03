## Gomplate Lab

Lab using https://docs.gomplate.ca/


gomplate -d config=myconfig.yaml -f input.tmpl

## myconfig.yaml
data:
  name: test

## input.tmpl
{
  "people": [
  {{ (datasource "config").data.name }}
  ]
}

---

gomplate -d person.json -f input.tmpl

## person.json
{
  "name": "Dave",
  "value" : "other"
}

## input.tmpl
{
  "people": [
  {{ (datasource "person").name }}
  ]
}

gomplate -f input.tmpl -d values.yaml --output-dir=dist'