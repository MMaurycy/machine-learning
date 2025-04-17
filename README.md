# Praca laboratoryjna: Bigram oraz word2vec (Natural Language Processing)

Autor: Marcin Przybylski
Data: 2025

## Opis

Niniejsza praca laboratoryjna stanowi praktyczne wprowadzenie do technik przetwarzania języka naturalnego (NLP), ze szczególnym uwzględnieniem modeli Bigram oraz reprezentacji wektorowych słów Word2Vec (wariant CBOW). Projekt obejmuje implementację, trening i analizę różnych modeli przy użyciu popularnych bibliotek (Gensim, PyTorch) na różnych zbiorach danych tekstowych. Dodatkowo wykorzystano techniki wizualizacji (PCA, t-SNE) i klasteryzacji (K-Means) do eksploracji i interpretacji wyników.

Całość prac została zrealizowana w środowisku Google Colaboratory.

## Zakres Prac (Zadania)

Laboratorium obejmuje następujące zadania:

1.  **Zadanie 1: Model Bigram - Generacja Imion (Częstości)**
    * Implementacja prostego modelu bigramowego opartego na zliczaniu częstości par znaków.
    * Wczytanie zbioru polskich imion (`IMIĘ_PIERWSZE.txt`).
    * Obliczanie macierzy prawdopodobieństw przejść między znakami (z wygładzaniem).
    * Definicja funkcji kosztu (NLL) i generowanie nowych imion na podstawie modelu.
    * Analiza wygenerowanych imion pod kątem ich prawdopodobieństwa wg modelu.

2.  **Zadanie 2: Model Bigram - Generacja Imion (Sieć Neuronowa)**
    * Implementacja modelu bigramowego przy użyciu prostej sieci neuronowej (jedna warstwa liniowa) w PyTorch.
    * Przygotowanie danych treningowych (kodowanie one-hot).
    * Definicja architektury sieci i procesu przejścia w przód (forward pass).
    * Trening modelu z funkcją kosztu NLL i regularyzacją L2.
    * Generowanie imion przy użyciu wytrenowanej sieci neuronowej.

3.  **Zadanie 4: Analiza Dialogów "The Simpsons" (Gensim Word2Vec)**
    * Wczytanie i preprocessing transkrypcji dialogów z serialu "The Simpsons" (`simpsons_script_lines.csv`).
    * Zaawansowany preprocessing tekstu (lematyzacja, usuwanie słów stopu - Spacy).
    * Tokenizacja i tworzenie bigramów za pomocą `gensim.models.phrases`.
    * Trenowanie modelu Word2Vec przy użyciu biblioteki Gensim.
    * Ewaluacja semantyczna modelu (`most_similar`, `doesnt_match`) na przykładzie postaci.
    * Wizualizacja wektorów słów (embeddingów) przy użyciu t-SNE.

4.  **Zadanie 5: Implementacja CBOW w PyTorch**
    * Przygotowanie danych treningowych (kontekst -> słowo centralne) z małego korpusu tekstowego.
    * Definicja architektury modelu CBOW (Continuous Bag of Words) w PyTorch (`nn.Embedding`, `nn.Linear`).
    * Trening modelu CBOW z funkcją kosztu NLLLoss i optymalizatorem Adam.
    * Ekstrakcja nauczonych embeddingów.
    * Klasteryzacja embeddingów za pomocą K-Means (`scikit-learn`).
    * Wizualizacja embeddingów i klastrów przy użyciu PCA (`scikit-learn`).

5.  **Zadanie 6: Analiza 4-gramów (Gensim Word2Vec)**
    * Pobranie i przetwarzanie pliku z sekwencjami słów (`raw_sentences.txt`).
    * Trenowanie modelu Word2Vec (CBOW) w Gensim na przetworzonych danych.
    * Analiza podobieństwa słów (`most_similar`) w kontekście 4-gramów (np. podobieństwo gramatyczne).
    * Wizualizacja embeddingów dla tokenów z 4-gramów za pomocą PCA.

6.  **Zadanie 7: Analiza Implementacji Word2Vec "From Scratch"**
    * Analiza kodu implementującego Word2Vec od podstaw (głównie NumPy).
    * Odpowiedzi na pytania dotyczące zastosowanej miary podobieństwa (kosinusowe) i sposobu wyszukiwania najbliższych sąsiadów (wyczerpujące porównanie).

7.  **Zadanie 8: Klasteryzacja Embeddingów CBOW (Notatnik Makemore)**
    * Klasteryzacja (K-Means) i wizualizacja (t-SNE) embeddingów uzyskanych z modelu CBOW (prawdopodobnie trenowanego na 4-gramach w notatniku Makemore).
    * Obsługa niezgodności rozmiarów między macierzą embeddingów a słownikiem.

8.  **Zadanie 9 (Bonus): Przewidywanie Ostatniego Słowa 4-gramu (PyTorch CBOW)**
    * Przygotowanie dedykowanego zbioru danych zawierającego tylko 4-gramy.
    * Definicja i trening modelu CBOW w PyTorch do przewidywania czwartego słowa na podstawie pierwszych trzech.
    * Testowanie modelu i analiza wyników predykcji (obserwacja potencjalnego przeuczenia).

## Technologie i Biblioteki

* Python 3
* Google Colaboratory
* PyTorch
* Gensim
* NumPy
* Pandas
* Scikit-learn (sklearn)
* Spacy
* Matplotlib / Seaborn (do wizualizacji)
* wget (do pobierania danych)

## Uruchomienie

Wszystkie zadania zostały zaimplementowane i wykonane w notatniku Google Colaboratory. Dostęp do notatnika:

* **Notatnik Roboczy Colab:** [https://colab.research.google.com/drive/1rTfWR7hWEWjju0BuYifdH3jyyPwRUsrx?usp=sharing](https://colab.research.google.com/drive/1rTfWR7hWEWjju0BuYifdH3jyyPwRUsrx?usp=sharing)

Instrukcje i materiały źródłowe:

* **Instrukcja do Zajęć (Google Docs):** (Link podany w raporcie, jeśli potrzebny)

## Podsumowanie Wyników

* Modele Bigram (zarówno częstościowy, jak i neuronowy) potrafią nauczyć się podstawowych zależności sekwencyjnych na poziomie znaków i generować proste sekwencje (imiona).
* Word2Vec (Gensim) efektywnie uchwycił relacje semantyczne między słowami (w tym postaciami) w dialogach "The Simpsons".
* Implementacja CBOW w PyTorch, nawet na małym zbiorze, pozwoliła na naukę wektorowych reprezentacji słów odzwierciedlających kontekst.
* Analiza 4-gramów pokazała zdolność Word2Vec do grupowania tokenów o podobnych funkcjach gramatycznych.
* Wizualizacja (PCA, t-SNE) i klasteryzacja (K-Means) okazały się użytecznymi narzędziami do interpretacji i zrozumienia przestrzeni embeddingów.
* Zadanie bonusowe zademonstrowało możliwość wykorzystania CBOW do przewidywania sekwencji, ale również uwypukliło ryzyko przeuczenia na ograniczonych danych.
