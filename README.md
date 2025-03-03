# UML

Uppgift 3 - Redovisning
Modellera Mera
Skapa och redovisa ett omfattande UML Klassdiagram för ditt/ert valda system.
Instruktioner:
I grupper ska ni använda era tidigare diagram och den kunskap ni fått under kursen för att
skapa ett detaljerat och välstrukturerat klassdiagram som beskriver den datamodell och de
relationer som används i ert valda system. Därefter ska ni redovisa diagrammet för resten av
klassen.
Grupper
● Det är fritt att välja grupper om max 4 personer.
● Vill man göra redovisningen själv så behöver man inte täcka alla delar.
● Maila mig eller skriv på Teams vilka grupper ni jobbar i så att jag kan koordinera
redovisningstillfället efter behov.
Syfte
Att visa förståelse för hur klasser, attribut, relationer och metoder samverkar för att designa en
systemmodell, samt att öva på att kommunicera och förklara era designbeslut.
Arbetsuppgifter:
1. Skapa Klassdiagrammet:
○ Identifiera viktiga klasser i systemet och definiera deras attribut och metoder.
○ Visa relationer mellan klasser, inklusive association, aggregation, komposition
och arv.
○ Lägg till kardinalitet och identifiera roller där det är relevant.
2. Förbered Redovisningen:
○ Förklara varför ni valde de klasser och relationer som ingår i diagrammet.
○ Beskriv hur diagrammet kopplar till systemets funktionalitet och tidigare modeller
(flöden, komponenter, etc.).
○ Diskutera eventuella utmaningar ni stött på och hur ni löste dem.
3. Tillämpa bästa praxis:
○ Se till att diagrammet är tydligt, korrekt och återspeglar ert systems
kärnfunktioner.
○ Använd UML-standarder för att säkerställa att era diagram är konsekventa.
Krav på klassdiagrammet:
● Minst 6-8 klasser med tydligt definierade attribut och metoder.
● Minst tre olika typer av relationer (association, aggregation, arv eller komposition).
● Användning av UML-standarder för att representera relationer, kardinalitet och metoder.
● Tydlig koppling till systemets funktion och domän.
Krav på redovisningen:
Varje grupp har 5-10 minuter för att presentera sitt klassdiagram.
Redovisningen ska inkludera:
● En översikt över diagrammet.
● En förklaring av hur diagrammet kopplar till systemets funktioner.
● En beskrivning av valda relationer och deras betydelse.
● Diskussion om vad som fungerade bra och vilka utmaningar gruppen stött på.
Bedömningskriterier:
Kompletthet
Är alla viktiga klasser, attribut och metoder inkluderade?
Tydlighet
Är diagrammet och presentationen lättförståelig?
Korrekthet
Är relationer, kardinalitet och klassdefinitioner korrekta enligt UML-standarder?
Kommunikation
Är redovisningen välstrukturerad och tydlig?
Exempel:
Om ert valda system är ett Bokningssystem för sportaktiviteter, kan diagrammet inkludera:
Klasser:
Medlem, Bokning, Aktivitet, Tränare, Plats.
Relationer:
En Medlem kan ha flera Bokningar.
En Bokning är kopplad till en Aktivitet.
En Aktivitet har en Plats och en Tränare.
Metoder:
I Medlem: registrera(), bokaAktivitet().
I Bokning: bekräfta(), avboka().
Inlämning:
Klassdiagrammet ska lämnas in som en PDF eller bildfil innan redovisningen.
Ett kort dokument (max 300 ord) med en förklaring av diagrammet ska bifogas. Vill ni skriva ut i
pappersformat så funkar det också.
Spotify Exempel - Med mermaid
Spotify Exempel
User
+id: Int
+name: String
+email: String
+subscription: String
+paymentOption: PaymentOption
+createPlaylist(): Playlist
Kan byggas ut med fler betalningsalternativ
+id: Int
Playlist
+name: String
+user: User
+createdDate: Date
+addTrack(track: Track)
+removeTrack(track: Track)
<<interfacе»
TrackSearch
+TrackSearch(user: User)
PaymentOption
+name: String
+description: String
+id: Int
Track
+title: String
+length: Time
+artist: Artist
+album: Album
+playSong(user: User)
Album
Genre
+name: String
+description: String
+id: Int
+title: String
+releaseDate: Date
+artist: Artist
Artist
+id: Int
+name: String
+image: String
Koden till exemplet:
---
title: Spotify Exempel
---
classDiagram
class User {
+id: Int
+name: String
+email: String
+subscription: String
+paymentOption: PaymentOption
+createPlaylist(): Playlist
}
class Playlist {
+id: Int
+name: String
+user: User
+createdDate: Date
+addTrack(track: Track)
+removeTrack(track: Track)
}
class Track {
+id: Int
+title: String
+length: Time
+artist: Artist
+album: Album
+playSong(user: User)
}
class Artist {
+id: Int
+name: String
+image: String
}
class Album {
+id: Int
+title: String
+releaseDate: Date
+artist: Artist
}
class Genre {
+name: String
+description: String
}
class TrackSearch {
+TrackSearch(user: User)
}
<<interface>> TrackSearch
class PaymentOption {
+name: String
+description: String
}
User --> Playlist
Playlist --> Track
Track --> Artist
Track --> Album
Album --> Artist
Track --> Genre
TrackSearch ..|> Track
User --> PaymentOption
note for PaymentOption "Kan byggas ut med fler betalningsalternativ"
