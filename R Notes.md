
## 1. Getting Started

- **Embrace the Frustration:**  
Frustration is natural when you start programming in R. Every beginner encounters challenges—persistence and practice will lead to mastery.

## 2. Core Data Structures

### Vectors

- **Homogeneous Data:**  
An R vector can contain only one data type (atomic vectors include numeric, character, and logical).  
**Tip:** Do not mix data types in a single vector.

- **Recycling:**  
R automatically recycles vector elements during operations when lengths differ. Use with caution to avoid unexpected results.

### Lists

- **Heterogeneous Storage:**  
Lists can store elements of various types, including entire data frames.

- **Relation to Vectors:**  
Lists are a type of vector in R but support heterogeneous elements.

- **Indexing Lists:**
    - Use **single square brackets** `[ ]` to subset a list (this returns another list).
    - Use **double square brackets** `[[ ]]` to extract a single element by index or by name.

- **Analogy with Python:**  
Named lists in R are similar to dictionaries in Python, where elements can be accessed by name.

### Data Frames

- **Tabular Data Structure:**  
A data frame is R’s primary tool for handling tabular data. Each column is an atomic vector.

- **Subsetting:**  
Use the `[rows, columns]` notation to extract parts of a data frame. For more readable filtering, consider the `subset()` function.

- **Dimensions:**  
The `dim()` function returns a vector where the first element is the number of rows and the second is the number of columns.

- **Relational Data:**  
In data science, you might work with multiple related data frames rather than one monolithic table. Combining data (e.g., using `rbind()`) requires ensuring column consistency.

## 3. Indexing Conventions

- **Starting Index:**  
R indexes elements starting at 1 (unlike Python, which starts at 0).

- **Indexing with Brackets:**
    - For atomic vectors, use `[ ]` to retrieve one or more elements.
    - For lists, use `[[ ]]` to extract a single element or use `$` for named elements.

## 4. Functions and the Functional Paradigm

### Generic Functions

- **Consistent Behavior:**  
R functions are generic—they behave uniformly across different objects and always return an R object.

### Functional Programming Concepts

- **Higher-Order Functions:**  
Functions that take other functions as arguments form the basis of functional programming in R.

- **Vectorization vs. Loops:**  
R’s vectorized operations often make explicit loops unnecessary, leading to cleaner and more efficient code.

### Common Functional Tools

- **apply Family:**
    - `lapply(x, FUN)`: Applies a function to each element of a list or vector and always returns a list.
    - `sapply(x, FUN)`: Similar to `lapply` but attempts to simplify the output (e.g., to a vector or matrix).
    - `apply()`: Useful for applying functions over rows or columns of matrices.

- **Map and Reduce:**
    - `Map()`: Applies a function to the corresponding elements of one or more lists.
    - `Reduce()`: Successively combines elements of a vector using a binary function (e.g., merging multiple data frames with `rbind()`).

## 5. Data Types and Operators

- **Primary Data Types:**
    - **Numeric:** Includes both double and integer types.
    - **Character:** Represents strings.
    - **Logical:** Consists of boolean values (`TRUE`/`FALSE`).

- **Operators as Functions:**  
    In R, operators (such as `+`, `-`, etc.) are functions. The assignment operator `<-` can be quickly entered using the shortcut Alt + minus.

## 6. Writing Clean, Reusable Functions

- **Design for Reusability:**  
Keep in mind that your functions may be used by others. Write clear, well-documented functions with appropriate default values for arguments.

- **Higher-Order Functions:**  
Use functions that accept other functions as parameters to create flexible and modular code.

## 7. The Tidyverse: dplyr and ggplot2

### dplyr

- **Non-Destructive Workflow:**  
dplyr functions (like `filter()`, `mutate()`, etc.) always create new data frames without altering the original. Use the assignment operator (`<-`) to save changes.

- **Grouping:**  
After using `group_by()`, subsequent operations (e.g., calculating means) are applied by group. Always include a count (`n()`) to ensure robust statistics.

- **Verbs Organization:**  
dplyr verbs are organized based on whether they operate on rows, columns, groups, or entire tables.

### ggplot2

- **Layered Grammar:**  
ggplot2 builds plots layer by layer. The order of layers matters because later layers are drawn over earlier ones.

- **Aesthetics:**  
In `aes()`, use `color` and `fill` to distinguish groups. Be aware that setting these outside `aes()` (in geoms) applies fixed values rather than mappings.


## 8. Statistical Functions

- **Distribution Functions:**  
R follows a consistent naming convention for statistical distributions (e.g., `dnorm`, `pnorm` for the normal distribution). Note that R parameterizes the normal distribution in terms of the standard deviation.

- **Covariance:**  
Use `cov()` to compute the covariance between vectors.

## 9. Miscellaneous Tips

- **Default Argument Values:**  
Many functions come with default values for arguments; be sure to read the documentation to understand these defaults.

- **Namespace Management:**  
To avoid conflicts when different packages contain functions with the same name, use the `package::function()` syntax.

- **Column Names in Tidyverse:**  
In the tidyverse, you typically do not need to quote column names.

- **Data Aggregation:**  
When plotting summary statistics (e.g., means) against group sizes, expect that the variability decreases as the sample size increases.

- **Keyboard Shortcuts:**  
In RStudio, use **Ctrl + Shift + M** for inserting the pipe operator (`%>%`), which is essential for chaining operations in the tidyverse.

# Serbian

## 1. Početak

- **Prihvatite frustraciju:**  
    Frustracija je prirodna kada počnete da programirate u R. Svaki početnik se susreće sa izazovima — upornost i praksa će vas dovesti do savladavanja jezika.

## 2. Osnovne strukture podataka

### Vektori

- **Homogeni podaci:**  
    Vektor u R-u može sadržavati samo jedan tip podataka (atomski vektori uključuju numeričke, karakterne i logičke vrednosti).  
    **Napomena:** Nemojte mešati tipove podataka u jednom vektoru.
- **Recikliranje:**  
    R automatski reciklira elemente vektora tokom operacija kada su dužine različite. Koristite ovu funkcionalnost pažljivo kako biste izbegli neočekivane rezultate.

### Liste

- **Heterogeno skladištenje:**  
    Liste mogu skladištiti elemente različitih tipova, uključujući čitave data frame-ove.
- **Veza sa vektorima:**  
    Liste su tip vektora u R-u, ali podržavaju heterogene elemente.
- **Indeksiranje lista:**
    - Koristite **jednostruke uglaste zagrade** `[ ]` da biste izdvojili podlistu (ovo vraća novu listu).
    - Koristite **dvostruke uglaste zagrade** `[[ ]]` da biste izdvojili jedan element po indeksu ili imenu.
- **Analogia sa Python-om:**  
    Liste sa imenima u R-u slične su rečnicima u Python-u, gde se elementi mogu pristupiti po imenu.

### Data frame-ovi

- **Tabelarna struktura podataka:**  
    Data frame je osnovni alat u R-u za rad sa tabelarnim podacima. Svaka kolona je atomski vektor.
- **Podskup podataka:**  
    Koristite notaciju `[redovi, kolone]` da biste izdvojili delove data frame-a. Za preglednije filtriranje, razmotrite upotrebu funkcije `subset()`.
- **Dimenzije:**  
    Funkcija `dim()` vraća vektor gde prvi element predstavlja broj redova, a drugi broj kolona.
- **Relacijski podaci:**  
    U data science-u, često se radi sa više povezanih data frame-ova umesto jedne monolitne tabele. Pri kombinovanju podataka (npr. korišćenjem `rbind()`) važno je obezbediti konzistentnost kolona.

## 3. Konvencije indeksiranja

- **Početni indeks:**  
    R indeksira elemente počevši od 1 (za razliku od Python-a koji počinje od 0).
- **Indeksiranje pomoću zagrada:**
    - Za atomske vektore, koristite `[ ]` da biste dohvatili jedan ili više elemenata.
    - Za liste, koristite `[[ ]]` da biste izdvojili jedan element ili operator `$` za elemente sa imenima.

## 4. Funkcije i funkcionalni paradigma

### Generičke funkcije

- **Dosledno ponašanje:**  
    R funkcije su generičke — ponašaju se dosledno za različite objekte i uvek vraćaju R objekat.

### Koncepti funkcionalnog programiranja

- **Funkcije višeg reda:**  
    Funkcije koje prihvataju druge funkcije kao argumente čine osnovu funkcionalnog programiranja u R-u.
- **Vektorizacija naspram petlji:**  
    Vektorizovane operacije u R-u često eliminišu potrebu za eksplicitnim petljama, što rezultira čistijim i efikasnijim kodom.

### Uobičajeni funkcionalni alati

- **Porodica funkcija apply:**
    - `lapply(x, FUN)`: Primenjuje funkciju na svaki element liste ili vektora i uvek vraća listu.
    - `sapply(x, FUN)`: Slično `lapply`, ali pokušava da pojednostavi izlaz (npr. u vektor ili matricu).
    - `apply()`: Koristan za primenu funkcija preko redova ili kolona matrica.
- **Map i Reduce:**
    - `Map()`: Primenjuje funkciju na odgovarajuće elemente jedne ili više lista.
    - `Reduce()`: Postepeno kombinuje elemente vektora koristeći binarnu funkciju (npr. spajanje više data frame-ova pomoću `rbind()`).

## 5. Tipovi podataka i operatori

- **Primarni tipovi podataka:**
    - **Numerički:** Uključuje tipove double i integer.
    - **Karakter:** Predstavlja tekstualne nizove.
    - **Logički:** Sastoji se od logičkih vrednosti (`TRUE`/`FALSE`).
- **Operatori kao funkcije:**  
    U R-u, operatori (kao što su `+`, `-`, itd.) su funkcije. Operator dodele `<-` se brzo unosi pomoću prečice Alt + minus.

## 6. Pisanje čistih, ponovo upotrebljivih funkcija

- **Dizajnirajte za ponovnu upotrebu:**  
    Imajte na umu da će vaše funkcije možda koristiti i drugi. Pišite jasne, dobro dokumentovane funkcije sa odgovarajućim podrazumevanim vrednostima argumenata.
- **Funkcije višeg reda:**  
    Koristite funkcije koje prihvataju druge funkcije kao parametre kako biste kreirali fleksibilan i modularan kod.

## 7. Tidyverse: dplyr i ggplot2

### dplyr

- **Nedestruktivan tok rada:**  
    dplyr funkcije (kao što su `filter()`, `mutate()`, itd.) uvek kreiraju nove data frame-ove bez menjanja originala. Koristite operator dodele (`<-`) da biste sačuvali izmene.
- **Grupisanje:**  
    Nakon upotrebe `group_by()`, naredne operacije (npr. računanje proseka) se primenjuju po grupama. Uvek uključite brojanje (`n()`) kako biste osigurali pouzdane statistike.
- **Organizacija glagola:**  
    Glagoli u dplyr-u organizovani su na osnovu toga da li operišu na redovima, kolonama, grupama ili celim tabelama.

### ggplot2

- **Slojevita gramatika:**  
    ggplot2 kreira grafikone sloj po sloj. Redosled slojeva je važan jer se kasniji slojevi crtaju preko ranijih.
- **Estetika:**  
    U `aes()`, koristite `color` i `fill` da biste razlikovali grupe. Imajte na umu da podešavanje ovih opcija van `aes()` (u geoms funkcijama) primenjuje fiksne vrednosti, a ne mapiranja.
- **Prečice na tastaturi:**  
    U RStudio-u, koristite **Ctrl + Shift + M** za umetanje operatora cevi (`%>%`), koji je ključan za povezivanje operacija u tidyverse-u.

## 8. Statističke funkcije

- **Funkcije za raspodele:**  
    R koristi konzistentnu konvenciju imenovanja za statističke raspodele (npr. `dnorm`, `pnorm` za normalnu raspodelu). Imajte na umu da R parametrizuje normalnu raspodelu koristeći standardnu devijaciju.
- **Kovarijansa:**  
    Koristite `cov()` da biste izračunali kovarijansu između vektora.

## 9. Razni saveti

- **Podrazumevane vrednosti argumenata:**  
    Mnoge funkcije dolaze sa podrazumevanim vrednostima argumenata; obavezno pročitajte dokumentaciju da biste ih razumeli.
- **Upravljanje imenskim prostorom:**  
    Kako biste izbegli konflikte kada različiti paketi imaju funkcije istog imena, koristite sintaksu `paket::funkcija()`.
- **Imena kolona u tidyverse-u:**  
    U tidyverse-u, obično nije potrebno navoditi imena kolona u navodnicima.
- **Agregacija podataka:**  
    Kada prikazujete sumarne statistike (npr. proseke) u odnosu na veličinu grupe, očekujte da varijabilnost opada kako se veličina uzorka povećava.

---