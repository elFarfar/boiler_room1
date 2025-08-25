2025-08-25 Ahmad Ardal
Deferred Deep Linking Solution
**Problemet**

Ett bolag samarbetar med influencers som delar unika länkar för att locka nya användare till att
registrera sig på bolagets plattform. Varje influencer får en egen länk med ett ID som gör det
möjligt att spåra vilken influencer som har värvat en viss användare. Exempel:

https://www.bolaget.se/signup?influencer=sara&source=instagram
Problemet är att många följare inte slutför registreringen direkt när de klickar på länken. När en
följare klickar på länken i till exempel Instagram, TikTok eller Facebook öppnas länken ofta i en
inbyggd webbläsare i själva appen (så kallad in-app browser). Det är en förenklad webbläsare som
körs inne i appen och inte i användarens vanliga webbläsare som Chrome eller Safari.


Många användare vill först läsa mer om bolaget innan de registrerar sig. Därför stänger de den
inbyggda webbläsaren i appen och öppnar istället sin vanliga webbläsare, som Safari eller Chrome.
Där söker de ofta upp bolaget via Google eller skriver in webbadressen direkt. När de sedan
registrerar sig sker det alltså inte via influencerns länk, utan som om de kommit in från Google
eller direkt. Resultatet blir att kopplingen till den ursprungliga influencern försvinner, vilket gör att
bolaget inte kan registrera vem som faktiskt värvade användaren – något som skapar problem för
både bolaget och samarbetet med influencern.

**Uppgiften**
Din uppgift är att designa en teknisk lösning som kan identifiera och följa en användares session
även när de byter från en inbyggd webbläsare i en app till sin vanliga webbläsare. Målet är att
bolaget inte ska förlora viktig information om användarens ursprung – exempelvis vilken kampanj,
annons eller länk som ledde användaren till plattformen – även om registreringen sker vid ett
senare tillfälle och i en annan webbläsare.

**Exempel**

En användare klickar först på en länk:

https://www.bolaget.se/signup?influencer=sara&source=instagram

Länken öppnas i den inbyggda webbläsaren i Instagram. Användaren stänger dock den och går
senare in i Safari/Chrome och söker efter bolaget på Google. Alltså följande länk vid andra
besöket:

https://www.bolaget.se

När de slutligen registrerar sig via https://www.bolaget.se, ska systemet fortfarande kunna veta
att användaren från början kom via influencern Sara och plattformen instagram.

**Leverans**

Ni ska bygga en Express.js-server som visar en enkel landningssida med ett registreringsformulär.
När en användare registrerar sig ska systemet kontrollera om det finns metadata om kampanj,
influencer eller källa. Om sådan information finns ska den sparas tillsammans med användarens
konto. Lösningen ska dessutom kunna bevara och återanvända denna information även om
användaren först besökt sidan med spårningsdata och sedan återkommer utan den – till exempel i
en annan webbläsare eller i ett privat fönster.