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

## Search for all Resources

```sh 
curl -s http://localhost:8080/fhir/Patient
curl -s http://localhost:8080/fhir/Organization
```

## Search for Specimen of certain type

https://hl7.org/fhir/R4/search.html

```sh 
curl -s http://localhost:8080/fhir/Specimen?type=saliva
```

## Search for Specimen from certain Patient

```sh
curl -s http://localhost:8080/fhir/Specimen?subject=Patient/bbmri-1
```
