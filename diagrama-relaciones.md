# Noches de Humo — Diagramas de Relaciones

Estos diagramas usan sintaxis **Mermaid**. Puedes verlos renderizados en:
- VS Code (extensión "Markdown Preview Mermaid Support"), o
- pegando cada bloque en https://mermaid.live

Para mantenerlos legibles, se dividieron en 4 vistas en lugar de un único mega-diagrama con 150+ personajes (ver `personajes-noches-de-humo.md` para la lista completa).

---

## Diagrama 1 — Mando del M-19 en la toma del Palacio

```mermaid
graph TD
    subgraph HIST["Dirección histórica M-19 (fuera del Palacio)"]
        BATEMAN["Jaime Bateman †1983"]
        FAYAD["Álvaro Fayad 'el Turco'<br/>Comandante General"]
        IVAN["Iván Marino Ospina †ago.1985"]
        PIZARRO["Carlos Pizarro"]
        NAVARRO["Antonio Navarro Wolff"]
    end

    subgraph MANDO["Estado Mayor de la toma"]
        OTERO["1º Luis Otero 'Lucho'<br/>Comandante general operativo"]
        JACQUIN["2º Alfonso Jacquin 'el Negro'"]
        ALMARALES["3º Andrés Almarales<br/>(fase política)"]
        ELVENCIO["4º Guillermo Elvencio Ruiz 'Memo'<br/>(vanguardia)"]
        ARIEL["5º Ariel Sánchez<br/>(retaguardia)"]
    end

    subgraph APOYO["Apoyo directo / comunicaciones"]
        CLAUDIA["Claudia / Clara Helena Enciso 'la Mona'<br/>Comunicaciones"]
        PATRICIA["Patricia 'Patico'<br/>Jefe de comunicaciones"]
        MARIANA["Mariana / Irma Franco<br/>Abogada-guerrillera"]
        NATALIA["Natalia"]
        CARLITOS["Carlos 'Carlitos'"]
        GORDO["El Gordo<br/>Logística"]
        SALVADOR["Salvador<br/>Comandante suplente"]
        LAZARO["Lázaro<br/>Grupo de choque (no llegó a tiempo)"]
    end

    BATEMAN -->|reclutó/formó| OTERO
    BATEMAN -->|reclutó/formó| IVAN
    BATEMAN -->|reclutó/formó| FAYAD
    FAYAD -->|idea original + escoge comandante| OTERO
    FAYAD -->|escogió por su perfil nacional| ALMARALES
    FAYAD -.->|coordinó órdenes con| PIZARRO
    PIZARRO -.->|coautor orden sobre Laura| FAYAD

    OTERO --> JACQUIN
    OTERO --> ALMARALES
    OTERO --> ELVENCIO
    OTERO --> ARIEL
    OTERO -->|reclutó y dirigió| CLAUDIA
    OTERO -.->|comandante suplente si falla| SALVADOR
    OTERO -.->|logística/reclutamiento vía| GORDO

    ELVENCIO ---|pareja sentimental| CLAUDIA
    ALMARALES -->|protegida por orden de Otero| CLAUDIA
    PATRICIA ---|trabaja con| CLAUDIA
    ARIEL -.->|grupo de choque tardío| LAZARO
    ALMARALES -->|comanda en el baño a| NATALIA
    ALMARALES --> MARIANA
    ALMARALES --> CARLITOS
```

---

## Diagrama 2 — Rama judicial: quién murió, quién sobrevivió, lazos familiares

```mermaid
graph TD
    subgraph CORTE["Corte Suprema de Justicia — Sala Penal"]
        REYES["Alfonso Reyes Echandía<br/>Presidente de la Corte · MUERE"]
        GAONA["Manuel Gaona Cruz · MUERE<br/>(versión disputada)"]
        MEDINA["Ricardo Medina Moyano · MUERE"]
        MEDELLIN["Carlos Medellín · MUERE"]
        SERRANO["Pedro Elías Serrano · MUERE"]
        CALDERON["Fabio Calderón Botero · MUERE"]
        VELASQUEZ["Darío Velásquez Gaviria · MUERE"]
        GNECCO["José Gnecco · MUERE"]
        TAPIAS["Hernando Tapias Rocha · SOBREVIVE"]
        CAMACHO["Nemesio Camacho · SOBREVIVE"]
        ARCINIEGAS["Reinaldo Arciniegas · SOBREVIVE"]
        MURCIA["Humberto Murcia Ballén · SOBREVIVE"]
    end

    subgraph FAMILIA["Familia Reyes Echandía"]
        SIRENIA["Sirenia (esposa)"]
        YESID["Yesid Reyes (hijo)<br/>Negocia por teléfono toda la crisis"]
        EMIRO["Emiro (hijo)"]
        HIJOA["Alfonso hijo"]
        HIJAS["Sirenia (hija)"]
    end

    REYES --- SIRENIA
    REYES --- YESID
    REYES --- EMIRO
    REYES --- HIJOA
    REYES --- HIJAS

    REYES -->|murió junto a, en oficina de Serrano| SERRANO
    SERRANO --- MEDINA
    SERRANO --- CALDERON
    SERRANO --- VELASQUEZ
    SERRANO --- GNECCO

    MEDELLIN ---|amigo de toda la vida| UMANA["Eduardo Umaña Mendoza<br/>(abogado DD.HH.)"]
    GAONA -->|lideró negociación de rehenes| TAPIAS
    GAONA --- CAMACHO
    ARCINIEGAS -->|su descripción delató a| CARLITOS2["'Carlitos' (M-19)<br/>capturado/desaparecido"]
    MURCIA ---|reencuentro| ARCINIEGAS

    REYES ===|amistad de toda la vida desde 1953| DELGADO["Gral. Víctor A. Delgado Mallarino<br/>Director Policía Nacional"]
```

---

## Diagrama 3 — Cadena de decisión Gobierno/Militar durante la crisis

```mermaid
graph TD
    BETANCUR["Belisario Betancur<br/>Presidente de la República"]
    DELGADO["Gral. Delgado Mallarino<br/>Director Policía Nacional"]
    SAMUDIO["Gral. Samudio Molina<br/>Cmdte. Ejército / Min. Defensa"]
    PAREJO["Enrique Parejo<br/>Ministro de Justicia"]
    CASTRO["Jaime Castro<br/>Ministro de Gobierno"]
    SANIN["Noemí Sanín<br/>Ministra de Comunicaciones"]
    VILLEGAS["Álvaro Villegas Moreno<br/>Presidente del Senado"]
    VARGAS["Gral. Vargas Villegas<br/>Cmdte. Policía Bogotá"]
    REYES2["Alfonso Reyes Echandía<br/>(rehén)"]
    YESID2["Yesid Reyes (hijo)"]
    OTERO2["Luis Otero (M-19)"]
    GARCIA["Gabriel García Márquez<br/>(desde París)"]
    AGUDELO["John Agudelo Ríos<br/>Comisión de Paz"]

    BETANCUR -->|ordena llamar a su amigo| DELGADO
    DELGADO <-->|negocia cese al fuego| REYES2
    DELGADO <-->|contacta para ultimátum| OTERO2
    BETANCUR -->|decide no negociar, consulta expresidentes| VILLEGAS
    VILLEGAS <-->|intermediario telefónico constante| REYES2
    VILLEGAS -->|transmite amenaza de dinamita| BETANCUR
    PAREJO -.->|dice ser amigo de infancia de| ALMARALES2["Andrés Almarales (M-19)"]
    PAREJO <-->|choca por decisión de asalto| DELGADO
    CASTRO -.->|esposo de rehén Clara Forero| CLARA["Clara Forero de Castro"]
    SANIN -->|impone censura a| PERIODISTAS["Prensa (Ríos, Salgado, Amat, Gossaín)"]
    YESID2 -->|intenta canal de negociación con| PERIODISTAS
    GARCIA -->|llama a su viejo amigo| BETANCUR
    GARCIA -->|ofrece comisión encabezada por| AGUDELO
    AGUDELO -.->|oferta rechazada, vía Umaña, a| OTERO2
    DELGADO -->|recibe parte 'mision cumplida' de unidad que mata a| OTERO2
    VARGAS -->|coordina rescates con civil| RAMBO["'Rambo Criollo' (civil rescatista)"]
    SAMUDIO -->|acusa públicamente a, de ordenar retirar su seguridad| REYES2
```

---

## Diagrama 4 — La red de Eduardo Umaña (el hilo que conecta todos los bandos)

Este personaje es clave porque el libro lo usa para **tejer** a los tres bandos (M-19, judicial, gobierno) a través de sus relaciones personales.

```mermaid
graph LR
    UMANA["Eduardo Umaña Mendoza<br/>Abogado DD.HH. · asesinado 1998"]

    UMANA ---|pacto de amistad / seudónimo del libro| BEHAR["Olga Behar<br/>autora"]
    UMANA ---|defendió legalmente| ELVENCIO2["Guillermo Elvencio Ruiz (M-19)"]
    UMANA ---|defendió legalmente| JACQUIN2["Alfonso Jacquin (M-19)"]
    UMANA ---|defendió legalmente| NAVARRO2["Antonio Navarro Wolff (M-19)"]
    UMANA ---|defendió legalmente| GRABE["Vera Grabe (M-19)"]
    UMANA ---|amigo de infancia, padres compañeros de colegio| MEDELLIN2["Carlos Medellín (magistrado, muere)"]
    UMANA ---|conocía a, admiraba sin tratar| REYES3["Alfonso Reyes Echandía (magistrado, muere)"]
    UMANA ---|buscada por ella tras escapar| CLAUDIA2["Claudia / Clara Helena Enciso (M-19)"]
    UMANA -.->|conocido en prisión| OTERO3["Luis Otero (M-19)"]
    UMANA ---|asistió al funeral de Toledo Plata junto a| ALMARALES3["Andrés Almarales (M-19)"]
    UMANA ---|padre, amigo de su padre| PADRE["Umaña padre<br/>(abogado/congresista MRL)"]
    UMANA -.->|influido por| TORRES["Camilo Torres<br/>(cura guerrillero, ELN)"]
    UMANA ---|propuesto por| POVEDA["Rafael Poveda Alfonso"]
    UMANA ---|mediado por el rector| HINESTROSA["Fernando Hinestrosa<br/>Rector Externado"]
```

---

### Cómo leer estos diagramas
- `-->` o `--` = relación/interacción directa mencionada en el texto.
- `-.->` = relación indirecta, rumor, o mención de segunda mano.
- `<-->` = comunicación en ambos sentidos (ej. llamadas telefónicas).
- `===` = relación de **amistad personal de larga data** (el eje emocional de buena parte del libro).

Para el elenco completo (150+ nombres, incluyendo combatientes rasos, periodistas, familiares y rehenes del Consejo de Estado), consulta `personajes-noches-de-humo.md`.
