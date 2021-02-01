# Wstęp
Azure Databricks to implementacja platformy Apache Spark zintegrowana ze środowiskiem Azure służąca do analizy danych, oferuje ona dwa środowiska do tworzenia aplikacji wykorzystujących dane: Azure Databricks SQL Analytics oraz Azure Databricks Workspace. 

Azure Databricks SQL Analytics zapewnia łatwą w użyciu platformę dla analityków, którzy chcą uruchamiać zapytania SQL na data lake, tworzyć wiele typów wizualizacji w celu eksplorowania wyników zapytań z różnych perspektyw oraz tworzyć i udostępniać pulpity. 

Azure Databricks Workspace zapewnia interaktywny obszar roboczy, który umożliwia współpracę między inżynierami danych, naukowcami zajmującymi się danymi i inżynierami uczenia maszynowego. W przypadku potoku danych big data, dane (surowe lub ustrukturyzowane) są pozyskiwane na platformie Azure za pośrednictwem usługi Azure Data Factory w partiach lub przesyłane strumieniowo niemal w czasie rzeczywistym przy użyciu platformy Apache Kafka, Event Hub lub IoT Hub. Trafiają one do data lake na potrzeby trwałego, długoterminowego magazynowania w usłudze Azure Blob Storage lub Azure Data Lake Storage. 

 

# Apache Spark (Spark) 

Apache Spark (Spark) to silnik do przetwarzania danych przetwarzania danych dla dużych zestawów danych, oparty na licencji open source. Został zaprojektowany z myślą o zapewnieniu szybkości obliczeniowej, skalowalności i programowalności wymaganej w przypadku Big Data - szczególnie w przypadku przesyłania strumieniowego danych, danych wykresów, uczenia maszynowego i sztucznej inteligencji. Skaluje się poprzez dystrybucję pracy na wiele klastrów z wbudowanymi obliczeniami równoległymi oraz odpornością na błędy. Zawiera interfejsy API dla języków programowania, które są popularne wśród analityków danych i naukowców, w tym Scala, Java, Python i R. 

Apache Spark ma hierarchiczną architekturę master/slave. Sterownik Spark to węzeł główny, który kontroluje menedżera klastra, który zarządza węzłami roboczymi i dostarcza wyniki danych do klienta aplikacji. 

Na podstawie kodu aplikacji, Spark Driver generuje SparkContext, który współpracuje z menedżerem klastra - Standalone Cluster Manager od Apache Spark lub innymi menedżerami klastrów, takimi jak Hadoop YARN, Kubernetes czy Mesos - w celu dystrybucji i monitorowania wykonywania zadań we wszystkich węzłach. Tworzy również Resilient Distributed Datasets (RDD), który jest podstawą szybkiego przetwarzania danych w Apache Spark. 

 

# Resilient Distributed Datasets (RDD) 

Resilient Distributed Datasets (RDD) to odporne na uszkodzenia zbiory elementów, które mogą być dystrybuowane między wieloma węzłami w klastrze i nad którymi można pracować równolegle. RDD to podstawowa struktura w Apache Spark. 

Spark ładuje dane, odwołując się do źródła danych lub przez zrównoleglenie istniejącej kolekcji za pomocą metody zrównoleglającej SparkContext do RDD w celu przetworzenia. Po załadowaniu danych do RDD Spark wykonuje transformacje i akcje na RDD w pamięci. Spark również przechowuje dane w pamięci, chyba że w systemie zabraknie pamięci lub użytkownik zdecyduje się zapisać dane na dysku w celu ich trwałości. 

Każdy zestaw danych w RDD jest podzielony na logiczne partycje, które mogą być obliczane na różnych węzłach klastra. Ponadto użytkownicy mogą wykonywać dwa rodzaje operacji RDD: transformacje i akcje. Transformacje to operacje stosowane w celu utworzenia nowego RDD. Akcje służą do poinstruowania Apache Spark, aby zastosował obliczenia i przekazał wynik z powrotem do sterownika. 

 

# Directed Acyclic Graph (DAG) 

W przeciwieństwie do dwuetapowego procesu wykonywania w MapReduce Spark tworzy Directed Acyclic Graph (DAG) w celu planowania zadań i zarządzaniu węzłami roboczymi w klastrze. Ponieważ Spark działa i przekształca dane w procesach wykonujących zadania, DAG zwiększa wydajność, organizując węzły robocze w klastrze. To kontrolowanie zadań umożliwia tolerowanie błędów, ponieważ zarejestrowane operacje są ponownie używane na danych z poprzedniego stanu. 

 

# DataFrames i Datasets 

DataFrames to najpopularniejsze strukturalne interfejsy programowania aplikacji (API), reprezentują one tabelę danych z wierszami i kolumnami. DataFrames zapewniają jednolitość w różnych językach, takich jak Scala, Java, Python i R. 

Zestawy danych (Datasets) są rozszerzeniem ramek danych, które zapewniają obiektowy interfejs programowania. Zestawy danych są domyślnie zbiorem obiektów JVM o jednoznacznie określonym typie, w przeciwieństwie do DataFrames. 

Spark SQL umożliwia odczytywanie danych z DataFrames i magazynów danych SQL, takich jak Apache Hive. Zapytania Spark SQL zwracają DataFrame lub Dataset, gdy są uruchamiane w innym języku 

 

# Spark Core 

Spark Core jest podstawą dla wszystkich równoległych procesów przetwarzania danych i obsługuje planowanie, optymalizację, RDD i abstrakcję danych. Spark Core zapewnia funkcjonalną podstawę dla bibliotek Spark, Spark SQL, Spark Streaming, bibliotek uczenia maszynowego MLlib oraz przetwarzania danych wykresu GraphX. Spark Core i cluster manager dystrybuują dane w klastrze Spark i wyodrębniają je. Ta dystrybucja i abstrakcja sprawiają, że obsługa Big Data jest bardzo szybka i przyjazna dla użytkownika. 

 

# Spark API 

Spark zawiera różnorodne API, aby dostarczyć Spark jak najszerszemu gronu odbiorców. Spark SQL umożliwia interakcję z danymi RDD w sposób relacyjny. Spark ma również dobrze udokumentowany interfejs API dla Scala, Java, Python i R. Każdy język w Spark ma swoje specyficzne niuanse w sposobie obsługi danych. RDD, DataFrames i Datasets są dostępne w każdym języku API. 

 

# Apache Spark MLlib 

Jedną z najważniejszych funkcji Apache Spark jest uczenie maszynowe dostępne w Spark MLlib. Zapewnia ono gotowe do użycia rozwiązanie do przeprowadzania klasyfikacji i regresji, filtrowania zespołowego, grupowania, rozproszonej algebry liniowej, drzew decyzyjnych, lasów losowych, drzew wzmocnionych gradientem, częstego eksploracji wzorców, metryk oceny i statystyk. 

 

# Rozpoczęcie pracy na Azure Databricks 

Aby rozpocząć pracę na Databricks za pomocą Azure należy utworzyć usługę Azure Databricks na portalu Azure. Cena zależy od wybranego klastra w serwisie. Aby rozpocząć pracę należy wejść w serwis Azure Databriks i uruchomić obszar roboczy. 

Wszystkie obliczenia przeprowadzane są w klastrach, więc by móc rozpocząć pracę należy utworzyć przynajmniej jeden klaster. W ustawieniach można wybrać typ klastra, wersję Databricks, typ procesora, ilość worker-ów, jeśli wybierze się min 0, to podczas bezczynności klastra nie są naliczane opłaty, ponieważ żaden worker wtedy nie pracuje.  

Po utworzeniu klastra i jego uruchomieniu możliwa jest praca w serwisie Databricks. Podstawowym obszarem roboczym są notebooki, w których można programować i wykonywać zadania. Notebooki wspierają języki Scala, Java, Python oraz R. Możliwe jest także wykonywanie zapytań SQL do pracy na danych zapisanych w tabelach. Przesyłanie danych do tabeli jest przedstawione w notebooku “Import danych.ipynb”. 

 

# Funkcjonalności 

# Tabele i widoki  

Databricks posiada możliwość przechowywania danych w tabelach, które moża udostępnić różnym użytkownikom. Wszystkie przeprowadzane na nich zmiany są widoczne dla każdego z użytkowników. By pracować lokalnie na danych możliwe jest pobranie ich do dataframe lub utworzenie widoków tymczasowych, zwanych też tabelami tymczasowymi.  

Operacje na tabelach są możliwe za pomocą zapytań SQL. 

# DataFrame 

Dane z tabel oraz plików można przesyłać do DataFrame by pracować na nich w obrębie notebooków i klastrów. Poza formatem od Spark możliwe jest także wykorzystanie formaty Pandas, który inne metody i może być wykorzystany do zadań, w których Spark gorzej się sprawdza. 

# Funkcje 

Databricks posiada wbudowane funkcje ułatwiające pracę na danych. Mogą zostać wykorzystane do różnych funkcji takich jak wyświetlanie lub edycja danych. Przykładowe funkcje: 

 - count() - zlicza ilość wierzszy w dataframe 

 - cahe() - zapisuje dane w pamięci podręcznej do szybkiego użytku 

 - show() - wyświetla dane z dataframe w postaci konsolowej 

 - display() - wyświetla dane w bardziej przejrzystej postaci i posiada zaawansowane funkcje, takie jak tworzenie diagramów 

 - limit() - tworzy nowy dataframe pobierając wybraną ilość wierszy 

 - select() - tworzy nowy dataframe pobierając wiersze z wybranych kolumn 

 - drop() - tworzy nowy dataframe pomijając wybrane wiersze 

 - distinct() - wyszukuje i wybiera unikalne wartości wybranej kolumny oraz tworzy z nich nowy dataframe 

 - dropDuplicates() - działa na podobnej zadadzie co funkcja distinct, ale umożliwia wybieranie wielu kolumn do wybierania unikalnych wierszy 

Możliwe jest również definiowanie własnych funkcji, których nie ma w Databricks.  

# Diagramy 

Databricks umożliwia tworzenie diagramów na podstawie wybranych danych. Wystarczy wybrać z listy typ diagramu i edytować jego parametry. Jeśli te diagramy są nie wystarczające, możliwe jest także wykorzystanie bibliotek różnych języków to tworzenia diagramów. 

MLflow to platforma typu open source do zarządzania kompleksowym cyklem życia systemów uczenia maszynowego. Podstawowe składniki: 

  - Tracking: umożliwia śledzenie eksperymentów w celu rejestrowania i porównywania parametrów i wyników. 

  - Modele: umożliwiają zarządzanie modelami z różnych bibliotek ML i wdrażanie ich na różnych platformach. 

  - Projekty: Umożliwiają pakowanie kodu ML w formie nadającej się do wielokrotnego użytku w celu udostępnienia innym analitykom danych lub przeniesienia do produkcji. 

  - Rejestr modeli: umożliwia scentralizowanie magazynu modeli w celu zarządzania pełnym cyklem życia modeli: od przejściowego do produkcyjnego, z możliwością wersjonowania i opisywania. 

  - Udostępnianie modeli: umożliwia hostowanie modeli MLflow jako punktów końcowych REST. 

# Modele 

Modele MLflow to standardowy format pakietów modeli uczenia maszynowego, który może być używany w różnych narzędziach podrzędnych - na przykład w obsłudze w czasie rzeczywistym za pośrednictwem interfejsu API REST lub wnioskowania wsadowego w Apache Spark. Format definiuje konwencję, która pozwala na zapisanie modelu w różnych „smakach”(flavors), które mogą być zrozumiane przez różne dodatkowe narzędzia. 

Flavors to kluczowa koncepcja, która sprawia, że modele MLflow są bardzo użyteczne: są konwencją, której narzędzia wdrożeniowe mogą używać do zrozumienia modelu, co umożliwia pisanie narzędzi współpracujących z modelami dowolnej biblioteki ML bez konieczności integrowania każdego narzędzia z każdą biblioteką. MLflow definiuje kilka standardowych smaków, które obsługują wszystkie wbudowane narzędzia do wdrażania, takie jak „Python function”, która opisuje, jak uruchomić model jako funkcję Pythona. 

# Wnioski Modele 

Dzięki spostrzeżeniom, które uzyskaliśmy z analizy danych, przetworzyliśmy dane na zestawy uczące, testowe oraz walidujące w scikit-learning i PySpark (w PySpark wykonaliśmy tylko podział danych na dane testowe, ale można było też podzielić je na zestawy treningowe i walidacyjne, podobnie jak w scikit-learn). Skonstruowaliśmy modele regresji logistycznej w każdym frameworku, wytrenowaliśmy je i oceniliśmy, przeanalizowaliśmy wyniki AUC jako metryki i przyjrzeliśmy się krzywej ROC oraz macierzy pomyłek, aby uzyskać lepszy pojęcie tego, jak model sobie radził w przypadku modelu scikit-learn a także wykonaliśmy k-krotną walidację krzyżową, aby pomóc dostroić hiperparametr. 

# Reprodukcja 

Do reprodukcji rozwiązania wystarczy pobrać dane ze strony www.kaggle.com/mlg-ulb/creditcardfraud oraz zaimportować dane, w sposób podany w instrukcji Import danych.ipynb. 

 

 
