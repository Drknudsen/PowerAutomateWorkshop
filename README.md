# PowerAutomateWorkshop
Trin-for-trin guide til at udløse en flow på en tilfældig dato
Opret et planlagt flow:

Log ind på Power Automate og opret et nyt Planlagt cloud flow.
Indstil tidsplanen til at køre dagligt (eller med en frekvens, der passer til dine behov).
Initialiser variabler:

Tilføj en Initialiser variabel-handling for at gemme den aktuelle dato.
Navn: CurrentDate
Type: String
Værdi: formatDateTime(utcNow(), 'yyyy-MM-dd')
Tilføj en anden Initialiser variabel-handling for at gemme en tilfældig dag i måneden.
Navn: RandomDay
Type: Integer
Værdi: rand(1, 28) (forudsat at du vil have en tilfældig dag mellem 1 og 28)
Betingelse for at tjekke den tilfældige dato:

Tilføj en Betingelse-handling for at tjekke, om den aktuelle dag matcher den tilfældige dag.
Betingelse: dayOfMonth(utcNow()) er lig med variables('RandomDay')
Tilføj handlinger baseret på dine behov:

I Hvis ja-grenen af betingelsen, tilføj de handlinger, du vil udføre på den tilfældige dato.
For eksempel kan du sende en e-mail, poste en besked i Teams eller udløse en anden proces.
Gem og test dit flow:

Gem dit flow.
Test det for at sikre, at det kører dagligt og kun udfører handlingerne på den tilfældige dato.
Eksempel Flow
Trigger: Recurrence (dagligt)
Handling: Initialiser variabel CurrentDate
Handling: Initialiser variabel RandomDay
Betingelse: Tjek om dayOfMonth(utcNow()) er lig med variables('RandomDay')
Hvis ja: Tilføj dine ønskede handlinger (f.eks. send en e-mail)
Denne opsætning sikrer, at dit flow kører dagligt, men kun udfører de specificerede handlinger på en tilfældigt valgt dag i måneden.
