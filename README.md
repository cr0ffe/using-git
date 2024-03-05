# using-git

Setup
```bash
git init <arbitrary folder name>
cd <arbitrary folder name>
```

Add the **base** github repo
```bash
git remote add origin <github url>
```

ex
```bash
git remote add origin "https://github.com/elastic/elasticsearch.git"
```

Enable sparse checkout
```bash
git config core.sparseCheckout true
```

Grab folder path
ex
```bash
https://github.com/elastic/elasticsearch/tree/main/docs/reference/query-dsl
```
->
```bash
docs/reference/query-dsl/*
```

Echo that path into `.git/info/sparse-checkout`  
ex
```bash
echo "docs/reference/query-dsl/*" >> .git/info/sparse-checkout
```

Download the latest commit's files
```bash
git fetch --depth=1 origin main
git checkout main
```
