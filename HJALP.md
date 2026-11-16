# Antifon – frågor och svar
Det vanligaste som krånglar, och vad man gör. Hela bruksanvisningen finns på driftssidan under **Om**.

## Installera och starta

### Windows varnar för installationsfilen

Installationsfilen är inte kodsignerad än, så Windows känner inte igen den. Välj **Mer information** och sedan **Kör ändå**. Hämta bara filen från Antifons nedladdningssida.

### Var startar jag Antifon, och hur ser jag att det kör?

Starta med genvägen **Antifon** på skrivbordet eller i Startmenyn. Antifon kör i bakgrunden och syns som en ikon (**A**) nere till höger vid klockan: grön = kör, grå = startar, röd = stoppad. Ligger ikonen bakom pilen **^** kan du dra ut den till aktivitetsfältet.

### Driftssidan öppnas inte

- Dubbelklicka på ikonen **A** vid klockan, eller öppna `http://localhost:8080/admin` i webbläsaren på samma dator. 
- Är ikonen röd: högerklicka på den och välj **Starta Antifon igen**. Välj **Visa loggen** för att se varför den stoppade. 
- Finns ingen ikon: starta Antifon med genvägen. 

### Ikonen är röd eller Antifon stoppar direkt

Högerklicka på ikonen och välj **Visa loggen**; orsaken står på de sista raderna. Det vanligaste är att ett annat program redan använder samma port, eller att Antifon redan kör i ett annat fönster. Starta om datorn om du är osäker. Hjälper inte det: spara en felrapport från ikonens meny och skicka den till den som hjälper er.

### Jag vill göra om guiden från första starten

Öppna **Inställningar** på driftssidan; länken till guiden står överst. Inget som redan är inställt försvinner.

## Ljud

### Nivåmätaren rör sig inte

- Välj rätt ingång under **Gudstjänst → Ljud in** (ljudkortet som mixern är kopplad till). 
- Kontrollera att mixern skickar ljud på den utgången, och att sladden sitter i. 
- I Windows: **Inställningar → Sekretess och säkerhet → Mikrofon** ska tillåta att appar använder mikrofonen. 

### Röda staplar i vågformen

Ljudet är för starkt och klipper. Sänk nivån från mixern eller vrid ner ingångsnivån på ljudkortet.

### Lyssnarna hör ingenting under sången

Det är meningen: Antifon tolkar tal men inte sång och musik. Tolkningen kommer tillbaka när någon talar.

## Tolkning och OpenAI

### Checklistan säger att OpenAI-nyckeln saknas

Lägg in nyckeln under **Inställningar → OpenAI** och tryck **Prova nyckeln**. Nyckeln skapas på platform.openai.com under *API keys*, och kontot behöver ha betalning aktiverad.

### Tolkningen startar inte, eller loggen säger fel 401

Nyckeln är fel eller återkallad. Skapa en ny hos OpenAI och lägg in den under **Inställningar → OpenAI**.

### Fel 429 eller ”insufficient_quota”

Pengarna på OpenAI-kontot är slut. Fyll på hos OpenAI (Billing). Under **Inställningar → OpenAI-saldot** kan Antifon visa ungefär hur mycket som finns kvar och varna i tid.

### Vad kostar tolkningen?

Ungefär 2–3 USD per timme och språk som någon lyssnar på. Antifon tolkar bara de språk som används just då. Driftssidan visar kostnaden hittills i statusfältet.

## Lyssnarna

### Mobilen kommer inte åt sidan med QR-koden

- Utan publik adress måste mobilen vara på samma wifi som Antifon-datorn. 
- Med tillfällig adress byts adressen varje gång Antifon startas: använd QR-koden som driftssidan visar nu, inte en gammal utskrift. 
- Vill ni ha en utskriven kod som alltid gäller behövs en fast adress (**Inställningar → Publik adress**). 

### Sidan öppnas men det hörs inget i mobilen

- Tryck på **Börja lyssna** på sidan; mobiler spelar inte ljud förrän man tryckt. 
- Höj volymen och kontrollera att hörlurarna är anslutna. 
- Kontrollera på driftssidan att gudstjänsten är startad: lampan **Kyrkan** i statusfältet ska vara grön. 

### De som lyssnar hemifrån hör ingenting

Hemma hör man bara det som öppnats: med **Lösenord – Öppna** hör de som loggat in med lösenordet hela gudstjänsten, och med **Predikan (podd) – Starta** hör alla med länken predikan. Lamporna **Lösenord** och **Alla** i statusfältet visar vad som är öppet.

## Publik adress

### Vilken adress ska vi välja?

**Tillfällig adress** fungerar direkt utan konto, men byts vid varje start. **Fast adress** är samma alltid och kräver en egen domän och ett gratiskonto hos Cloudflare. **Ingen publik adress** räcker om alla lyssnar på kyrkans wifi. Valet görs under **Inställningar → Publik adress**.

### Den fasta adressen svarar inte

Öppna **Inställningar → Publik adress → Ställ in en fast adress** och tryck **Ställ in** igen; stegen visas och felet står där. Antifon använder en tillfällig adress så länge. Två datorer får inte ha samma fasta adress på samtidigt.

## Inspelning

### Jag startade en inspelning av misstag

Stoppa den. I en minut efteråt visar statusfältet **Fortsätt samma inspelning**, **Spara nu** och **🗑 Ta bort**.

### Var hamnar inspelningarna?

Under fliken **Inspelningar** på driftssidan. På disken ligger de i mappen som är vald under Inställningar; en installerad Antifon använder `%LOCALAPPDATA%\Antifon\inspelningar` om inget annat är valt.

## Uppdatera och avinstallera

### Hur uppdateras Antifon?

Antifon söker själv en gång i timmen. Under **Om → Uppdateringar** står det när en ny version finns; tryck **Uppdatera och starta om**. Det går inte medan något spelas in, tolkningen är på eller en gudstjänst börjar inom 30 minuter. Inställningar och inspelningar rörs inte.

### Hur avinstallerar jag?

Windows **Inställningar → Appar → Antifon → Avinstallera**. Du får frågan om inställningar, inspelningar och nycklar också ska tas bort; standard är att de sparas.

## När inget av detta hjälper

### Spara en felrapport

Felrapporten är en zip-fil med Antifons loggar, inställningarna och checklistan. Nycklar, lösenord, pushämnen och e-postadresser tas bort innan filen sparas. Inspelningar och manus följer inte med. Loggraderna kan innehålla namn på dem som loggat in på driftssidan.

- På driftssidan: **Om → Hjälp → Spara felrapport**. 
- Om Antifon inte startar: högerklicka på ikonen **A** vid klockan → **Spara felrapport** (filen hamnar på skrivbordet). Skicka filen till den som hjälper er med Antifon, och berätta vad ni gjorde när felet kom.
