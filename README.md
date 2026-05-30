Instrukcja instalacji i uruchomienia (Środowisko Anaconda)

Projekt został zrealizowany w środowisku **Jupyter Notebook** z wykorzystaniem dystrybucji **Anaconda**, co zapewnia pełną powtarzalność badań i automatyczne zarządzanie bibliotekami do obliczeń naukowych (np. `numpy`, `pandas`, `scikit-learn`).

### 1. Klonowanie repozytorium
Skopiuj pliki projektu na swój lokalny dysk za pomocą systemu kontroli wersji Git
### 2.Upewnij się, że surowe pliki zbioru danych pobrane z UNSW Canberra znajdują się w głównym folderze projektu (w tym samym katalogu, co notatniki .ipynb):

-UNSW_NB15_training-set.csv

-UNSW_NB15_testing-set.csv
### 3. Przygotowanie środowiska (Anaconda)
Zaleca się utworzenie dedykowanego środowiska, aby uniknąć konfliktów z innymi projektami. W terminalu Anaconda Prompt wykonaj następujące kroki:

Bash
# Utworzenie nowego środowiska o nazwie "ids_project" z odpowiednią wersją języka Python
conda create -n ids_project python=3.10 -y

# Aktywacja środowiska
conda activate ids_project

# Instalacja wymaganych bibliotek z pliku requirements
pip install -r requirements.txt

### 4. Uruchomienie potoku analitycznego w Jupyter Notebook
Po aktywowaniu środowiska uruchom serwer Jupyter Notebook:

Bash
jupyter notebook
Nastąpi otwarcie przeglądarki internetowej. Pliki należy otwierać i uruchamiać komórka po komórce (lub korzystając z opcji Run All) w ściśle określonej sekwencji:

feature_selection.ipynb – Ekstrakcja cech wolumetrycznych, redukcja wymiarowości (RFECV) oraz generacja wieloklasowych wykresów SHAP, oraz izolacja zbioru trudnego i stochastyczny trening architektur głębokich (GAN). Ten krok wygeneruje kluczowy plik UNSW_NB15_GAN_Balanced_main.csv.

model_train.ipynb – Optymalizacja hiperparametrów (XGBoost + Ridge) i finalna weryfikacja macierzy pomyłek w obliczu dryfu pojęciowego. 
