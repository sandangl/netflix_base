# Netflix Prize Contest -- Big Data 2024/2025

### [🇮🇹​ Italiano](#per-cominciare)
### [​🇬🇧​ English](#get-started)

---


## Per cominciare

### Come clonare questo repository

Dal momento che questo repository contiene file di grandi dimensioni, si rende necessario l'uso di [Git LFS](https://git-lfs.com/) per clonarlo. È possibile installarlo seguendo il link precedente.

Dopodiché, è sufficiente clonare il repository come al solito:
```bash
git clone https://github.com/sandangl/netflix_base.git
```
Poiché Git scarica solo i puntatori LFS per file di grandi dimensioni, sarà necessario scaricare anche i file effettivi. Per farlo, basta eseguire:
```bash
git lfs install
git lfs pull
```

### Come eseguire il codice

Tutto il codice viene fornito sotto forma di notebook Python. L'unico passo preliminare, consiste nell'eseguire lo script di preparazione:
```bash
./script/get_started.sh
```

Adesso è tutto pronto!

## Risoluzione dei problemi

Durante l'esecuzione, potrebbe succedere di imbattersi in alcuni dei seguenti problemi:

- **Out of Memory**: Questo accade a causa di limitazioni di memoria, che per impostazione predefinita sono adattate ai vincoli di Google Colab. Per risolvere il problema, si provi a modificare la configurazione:
   ```python
   spark = SparkSession.builder \
    .appName("Netflix Recommendation System") \
    .config("spark.executor.memory", "6g") \ # <-- modificare qui
    .config("spark.driver.memory", "6g") \ # <-- modificare qui
   ```
Dopo le modifiche è necessario riavviare il kernel.
È consigliato impostare approssimativamente metà della memoria totale disponibile.

- **BadZip: the file is not an archive** Questo si verifica quando gli i file puntati dagli oggetti LFS non sono ancora stati scaricati. Eseguire `git lfs install` quindi `git lfs pull` e riprovare.  È consigliato riavviare il kernel.

--- 


## Get Started

### How to clone this repository

Since this repository contains large files, [Git LFS](https://git-lfs.com/) is required for cloning. You can install it by following the link above.

Then, you can clone the repository as usual:
```bash
git clone https://github.com/sandangl/netflix_base.git
```
Because Git only pulls LFS pointers for large files, you will also need to fetch the actual files. To do this, run:
```bash
git lfs install
git lfs pull
```

### How to run the code

All the code is provided in the form of a Python Interactive Notebook.

The only preliminary step is to run the setup script:
```bash
./script/get_started.sh
```
Now you are all set!

## Troubleshooting

During execution, you may run into some of the following issues:

- **Out of Memory**:This happens due to memory limitations, which are tuned by default for Google Colab's constraints. To fix this, try adjusting the configuration:
   ```python
   spark = SparkSession.builder \
    .appName("Netflix Recommendation System") \
    .config("spark.executor.memory", "6g") \ # <-- change here
    .config("spark.driver.memory", "6g") \ # <-- change here
   ```
   A kernel restart is required after changes.
   We recommend setting approximately half of your overall available memory.
- **BadZip: the file is not an archive**: This occurs when LFS objects have not yet been downloaded. Please run `git lfs install` followed by `git lfs pull`, and then try again. A kernel restart is recommended.