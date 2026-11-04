# Tasca 2:Git, viatjant pel tempsy

## Presentació de l'activitat

### Durada de l'activitat

La durada prevista de l'activitat és 2 hores a classe.

### Objectius específics de l'activitat

- Gestionar un repositori mitjançant Git i GitHub.
- Generació de documentació en format Markdown.

### Competències treballades

m) Organitzar i desenvolupar el treball assignat mantenint unes relacions professionals adequades en l’entorn de treball.

### Resultats d'aprenentatge i criteris d'avaluació

- 1713.4. Realitza el seguiment de l'execució de les activitats plantejades, verificant que es compleix amb la planificació.
- 1713.5. Transmet informació amb claredat, de manera ordenada i estructurada.

#### Criteris d'avaluació

4.6 Defineix i elabora la documentació necessària per a l'avaluació de les activitats i del projecte en el seu conjunt.

5.1 Manté una actitud ordenada i metòdica en la transmissió de la informació.

5.4 Coneix els termes tècnics en altres llengües que siguin estàndards del sector.

### Continguts

- Control de versions.

### Capacitats clau treballades

- Autonomia
- Organització del treball
- Resolució de problemes
- Responsabilitat

### Semàfor ús de la IA

🟠 Aquesta activitat permet un ús parcial o restringit.

Permès per com a eina de suport en la millora de la redacció dels informes, cerca preliminar d'informació, estructuració d'idees o explicació de conceptes teòrics complexos.

**Condicions**: Cal processar, entendre i validar sempre els resultats rebuts. Està totalment prohibit copiar l'enunciat d'un exercici directament al xat de la IA i enganxar la resposta generada per al lliurament final sense treball propi ni anàlisi crítica.

## Enunciat de l'activitat

### Requeriments previs

- Compte de GitHub actiu
- Git instal·lat al vostre ordinador
- Editor VS Code
- Identitat de git configurada al repositori local:

  ```bash
    git config user.name "Nom Cognoms"
    git config user.email el_teu_correu@mataro.epiaedu.cat
  ```

### Descripció de l'activitat

En aquesta activitat treballarem un aspecte fonamental de control de versions: l'historial de versions. Veurem com podem viatjar en el temps dins del nostre repositori i recuperar versions anteriors dels fitxers.

#### Part 1: Bones pràctiques en la documentació de commits

Tot i que ja esteu acostumats a fer commits, és important que aquests estiguin ben documentats. Per això, en aquesta part de l'activitat, revisarem els vostres últims commits i els millorarem si cal.

Un bon missatge de commit permet a qualsevol company de l'equip entendre què s'ha fet sense haver de llegir tot el codi.

- Format recomanat per a un missatge de commit:

  `<Tipus>: descripció curta en imperatiu`.
  
  Alguns del tipus de commit més habituals són:

  - `feat`: afegir una nova funcionalitat
  - `fix`: corregir un error
  - `docs`: canvis en la documentació
  - `style`: canvis en l'estil del codi (formatació, espais, etc.)

- Escriu en imperatiu/present: Exemple "afegeix la funcionalitat de login" en lloc de "afegit la funcionalitat de login".

- Commits **atòmics**: Cada commit hauria de representar un canvi lògic i complet. No barregis la correcció d'un fitxer d'una tasca amb la redacció del README en un sol commit.

**Exercici pràctic**: crear commits estructurats

1. Crea un fitxer anomenat README.md a dins la carpeta tasca02 amb una breu descripció de la tasca, com un breu enunciat.
1. Fes el teu primer commit seguint la convenció de missatges de commit que hem vist abans:

   `"docs: inicialitza la documentació de la tasca 2"`

1. Crea un fitxer de configuració de la xarxa anomenat `interfaces.yaml` amb el següent contingut:

   ```yaml
   network:
     version: 2
     renderer: networkd
     ethernets:
       eth0:
         dhcp4: true
   ```

  i fes un commit following les bones pràctiques, tenint clar que és del tipus `feat`.

#### Part 2: L'historial del repositori

Com a profesional, sovint hauràs de revisar l'historial del repositori per saber qui va fer un canvi determinat o quin dia es va modificar una configuració concreta.

1. Observa l'historial del teu repositori amb l'historial detallat, identificant la informació disponible per cada commit, executant a la terminal la comanda:

  ```bash
  git log
  ```

1. Compara el resultat amb l'historial resumit, executant a la terminal la comanda:

  ```bash
  git log --oneline
  ```

1. Usa l'eina gràfica de l'editor VS Code per veure l'historial del repositori i comparar-lo amb el que has vist a la terminal.

1. Inspecciona els canvis exactes del darrer commit amb la comanda:

  ```bash
  git show HEAD
  ```

  Observa també la mateixa informació amb l'eina gràfica de l'editor VS Code, seleccionant el darrer commit.

  > **Nota**: `HEAD` és un punter que apunta al darrer commit del teu repositori, ja que l'historial funciona com una pila, on el darrer commit és el primer que es mostra.

#### Part 3: Recuperar versions anteriors del working directory

Imagina que estàs editant el fitxer interficies.yaml i, per error, esborres informació crucial o comets una erada de tecleig. Com que encara no has fet git commit, pots descartar els canvis del Working Directory i tornar el fitxer a l'estat del darrer commit.

1. Simularem un error humà editant el fitxer interficies.yaml

  ```yaml
  network:
    version: 2
    renderer: networkd
    ethernets:
      enps03:
        dhcp4: true
  ```

1. Observa l'estat del repositori. A l'editor VS Code, veuràs que el fitxer interficies.yaml apareix amb una `M`, indicant que ha estat modificat. A la terminal, executa la comanda al terminal per comprovar com t'indica aquesta situació:

  ```bash
  git status
  ```

1. Desfem els canvis del fitxer interficies.yaml i tornem-lo a l'estat del darrer commit. Això es pot fer gràficament a l'editor VS Code, fent clic amb el botó dret sobre el fitxer i seleccionant l'opció "Discard changes". També es pot fer des de la terminal amb la comanda:

  ```bash
  git restore interfaces.yaml
  ```
  
  Una vegada fet això, comprova que el fitxer ha tornat a l'estat del darrer commit.

### Què cal lliurar, on i com?

- Documentació de l'activitat en format Markdown a la carpeta `tasca02` del vostre repositori del projecte 4.

## Material de suport

- Material propi.[Guia 1. Iniciació a Git, GitHub i Visual Studio Code](https://github.com/SMX-ProjecteIntermodular/Guies/blob/main/git-github/01-iniciacio-git-github-vscode.md)

- Material propi. [Guia 2. Treballant en el repositori amb Git](https://github.com/SMX-ProjecteIntermodular/Guies/blob/main/git-github/02-comandes-git.md)

- Material propi. [Guia 3. Markdown per treballar amb repositoris](https://github.com/SMX-ProjecteIntermodular/Guies/blob/main/git-github/03-markdown.md)

- Material propi. [Guia 4. Creació de repositoris a partir de plantilla](https://github.com/SMX-ProjecteIntermodular/Guies/blob/main/git-github/04-crear-repositoris.md)

- Material propi. [Guia 5. Resolució de conflictes amb Git](https://github.com/SMX-ProjecteIntermodular/Guies/blob/main/git-github/05-resolucio-conflictes.md)

- GitHub. [Documentación de GitHub](https://docs.github.com/es)
