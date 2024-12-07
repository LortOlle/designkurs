Laddningstider
=======================

Jag ska studera laddningstider och användbarhet på tre olika hemsidor. Både för att lära mig de verktyg man kan använda för att studera laddtid men också för att studera vad det är som är flaskhalsar för sidladdning.

Urval
-----------------------

Jag har valt att studera några olika typer av webbplatser. Den första är YouTube.com. Min tanke var att studera hur de kan ladda så många video miniatyrer på relativt kort tid. Min andra hemsida är Aftonbladet.se. Min tanke där var att det är relativt mycket bilder och anonser vilket borde göra sidan långsam. Den sista sidan jag ska testa är wikipedia. Det borde vara en relativt snabb sida med tanke på att det är övervägande textinnehåll.

Metod
-----------------------

Jag undersöker sidan med hjälp av Chromes inbyggda "Lighthouse" verktyg. Jag kommer titta på "Fist content paint", "Largest Contentful Paint", "Total Blocking Time", "Cumulative Layout Shift" och "Speed Index". 

"First content paint" mäter hur lång tid det tar innan första innehållet syns på skärmen. Det är ett viktigt mått eftersom det är den tiden användaren måste vänta innan den ser något innehåll. Man kan ha tålamod att vänta på några element som är långsamma att ladda men om sidan är helt tom en längre tid kommer användaren bli irriterad.

"Largest Contentful Paint" är ett mått på hur lång tid det tar innan det största elelementet är laddat på sidan. Det är intressant eftersom när det är laddat borde en stor del av innehållet vara laddat.

"Total Blocking Time" är ett mått på hur lång tid, efter first content paint, det tar innan det går att interagera med sidan. Tid för t.ex. javascript att laddas etc. Det är ett bra mått eftersom en sida kan upplevas slö om sidan och länkar är laddade men fungerar inte att trycka på.

"Cumulative Layout Shift" mäter hur mycket sidans element "hoppar runt" på sidan. Om en rubrik laddar först och en stor rubrik ovanför laddar in efter kan bilden flyttas ner när rubriken dyker upp. Detta kan vara störande om användaren försöker trycka på en länk som flyttas när användaren trycker.

"Speed Index" är ett mått på hur snabbt innehåll är synligt på sidan. Detta kan ju ge en övergripande bild över hur lång tid användaren måste vänta.

Alla bifogade bilder av analyssammanställningar är från mobiltester eftersom de generellt ger sämre resultat så det finns mer att analysera.

Resultat
-----------------------

En sammanställning av resultatet är bifogat längre ner.

![Youtubes analys](%assets_url%/img/LHyoutube.jpg){.analys-img}

Youtube går som förväntat lite långsammare. Det är dock inga större laddningstider med tanke på den stora mängden videos som ska ladda in. Det är också över en sekund i total blocking time. Anledningen till att performance får så lågt betyg är de långa laddtiderna och den stora mängden DOM element (1934 stycken). Sidan fick också kritik för den stora mängden oanvänd javascript och css som laddas in. Det låga betyget på "Best Practices" berodde på den stora mängden tredjeparts cookies.

![Aftonbladet analys](%assets_url%/img/LHaftonbladet.jpg){.analys-img}

Aftonbladet har en relativt kort laddtid. Det stora problemet är istället tiden länkar etc är blockerade. Detta kan leda till irritation hos användare. Lighthouse menar att laddtiden beror till stora delar på laddning av javascript. Sidan tappar några poäng på "Accessability" eftersom alla element inte har några namn satta. Det gör att skärmläsare kommer läsa upp knappen dom "button" istället för något som säger lite mer. Även här tappas poäng på best practices på grund av mängden tredjepartscookies

![Wikipedia analys](%assets_url%/img/LHwiki.jpg){.analys-img}

Wikipedia får som väntat bättre betyg än de andra med tanke på den relativt simpla layouten och övervägande textinnehåll. Anledningen till att de tappar 10 poäng på Perfomance är att det ändå tar relativt lång tid att ladda in det största elementet samt att sidan dirigerar om till en separat mobilsida vilket tar 0,8s extra. Accessability är det lägsta betyger. Det beror på att flera bilder inte har något "alt" attribut och några form element inte har några labels. Sidan är också den enda som inte har full pott på search engine optimization. Det beror på att det inte finns någon "meta" och att vissa bilder inte har något "alt" attribut.


<div class = "spreadsheet-container">
    <iframe title = "Speadsheet" class = "spreadsheet" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRv8of8X3in0SnmoiWVBE7NZn3Ann6MNwggWuEhPy7oXb0AgrJxSEOETXGZibyJFgZfn5X1N7rm3Ajj/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false"></iframe>
</div>

Analys
-----------------------

Jag tycker att de har lyckats bra med att få laddtiden att vara rimlig. Det är ju inte direkt förvånande att ett företag som google har en hemsida som fungerar bra. Det är dock lite överraskande att de presterar så pass dåligt på "Performance" testerna. Om det finns javascriptkod och CSS som inte används så borde det kunna effektiviseras. Om koden delas upp så endast relevant kod används på varje sida bör laddningstiden förbättras.

Det är också förvånande att en så stor sida som Youtube andänder så mycket tredjepartscookies. De är anledningen att de presterar så dåligt på sina egna test för "Best practice".

Aftonbladet presterar relativt bra. Det är dock lite konstigt att de inte sätter name attribut på elementen. Det är ju ett relativt simpelt tillägg. De använder också mycket tredjepartscookies men det är mer ursäktat för aftonbladet än för google.

Wikipedia har väldigt bra resultat om man kör testet i desktop miljö. Det är på Search engine optimization de får sämst resultat vilket är konstigt med tanke på att wikipedia borde vara gjort för att sökning.

Referenser
-----------------------

[Youtube.com](https://www.youtube.com/){.link}

[Aftonbladet.se](https://www.aftonbladet.se/){.link}

[sv.Wikipedia.org](https://sv.wikipedia.org/wiki/Portal:Huvudsida){.link}

[Förklaring av Lighthouse](https://developer.chrome.com/docs/lighthouse/performance/performance-scoring){.link}

Skrivet av
-----------------------

Erik Olsson.