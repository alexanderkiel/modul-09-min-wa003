## Generator

https://github.com/samply/bbmri-fhir-gen

```sh
bbmri-fhir-gen -n 10 fhir-data
```

## FHIR Server

https://github.com/samply/blaze

```sh
docker run -d --name blaze -p 8080:8080 samply/blaze:0.34
```

```sh
curl -s -H 'Content-Type: application/fhir+json' -d @fhir-data/biobank.json http://localhost:8080/fhir  
curl -s -H 'Content-Type: application/fhir+json' -d @fhir-data/transaction-0.json http://localhost:8080/fhir  
```

```sh 
curl -s http://localhost:8080/fhir/Patient
```
