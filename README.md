# Somali Football Hub

Bog kubadda cagta oo bilaash ah, Af-Soomaali iyo Ingiriisi ku qoran, oo ku shaqeeya taleefoon, tablet iyo kombuyuutar. Waxaa ka kooban hal fayl oo keliya: `index.html`.

## Digniin muhiim ah: xog tusaale ah

- **Xog tusaale ah (la sameeyay):** natiijooyinka, xaaladda ciyaaraha, taariikhaha, saacadaha bilowga, miisaska horyaallada, wararka, qoraalka ciyaartoyda iyo macluumaadka kubadda Soomaaliya. Dhammaan waxaa lagu calaamadiyay **TUSAALE** ama **TIJAABO**.
- **Macluumaad guud:** magacyada kooxaha, magaalooyinka, garoommada iyo sannadaha la aasaasay. Fadlan xaqiiji, waayo wax way isbeddelaan.
- Bogga **ma xirna** xog toos ah. Wax natiijo toos ah ma muujiyo.
- Astaamaha kooxaha waa calaamado asal ah, ma aha astaamaha rasmiga ah.

## Waxa bogga ku jira

Hore, Natiijooyin Toos, Jadwalka, Wararka, Horyaallada (Premier League, La Liga, Serie A, Bundesliga, Ligue 1, Champions League), Kooxaha, Miisaska, Ciyaartoyda, Kubadda Soomaaliya, Raadin iyo shaandhayn, iyo badhan luuqadda lagu beddelo (EN / SO).

## Sida loo daabaco (GitHub Pages)

1. Hubi in faylka `index.html` uu ku jiro repository-gaaga (heerka ugu sarreeya, ma aha gudaha galka).
2. Tag **Settings** → **Pages**.
3. Hoostiisa **Build and deployment → Source** dooro **Deploy from a branch**.
4. **Branch** dooro **main** iyo **/ (root)**, kadibna taabo **Save**.
5. Sug 1 ilaa 3 daqiiqo. Linkigaaga wuxuu noqonayaa:
   `https://USERNAME.github.io/somali-football-hub/`

## Sida loo cusboonaysiiyo

Fur `index.html` → taabo astaanta qalinka (Edit) → beddel → **Commit changes**. Bogga wuu cusboonaanayaa ilaa hal daqiiqo gudaheed.

Xogta waxaa laga beddelaa qaybta `<script>` ee faylka hoostiisa:

- `I18N`: qoraalka oo dhan ee Soomaali iyo Ingiriisi
- `LEAGUES`, `TEAMS`, `MATCHES`, `TABLES`, `NEWS`, `PLAYERS`, `COMPS`, `NATIONAL`: xogta

## Si loo xiro xog toos ah

GitHub Pages waxay martigelisaa faylal taagan oo keliya, sidaa darteed xogta toosan waa inay ka timaadaa adeeg dibadda ah:

- **Natiijooyin toos ah, jadwal, miisas:** API xog kubadeed sida football-data.org, API-Football ama TheSportsDB. Intooda badan waxay u baahan yihiin koonto bilaash ah iyo furaha API, qorshayaasha bilaashka ahna waxay leeyihiin xadka codsiyada, horyaallada iyo dib-u-dhaca.
- **Furayaasha API:** furaha ku jira koodka bogga qof walba wuu arki karaa. Isticmaal proxy yar oo bilaash ah (tusaale Cloudflare Worker) oo furaha haysta.
- **Wararka:** RSS feed ama API wararka. Hubi shuruudaha bixiye kasta ka hor intaadan dib u daabicin ciwaanno ama sawirro.
- **Kubadda Soomaaliya:** API-yada waaweyn marar dhif ah ayay daboolaan horyaallada Soomaaliya, sidaa darteed gacanta ku cusboonaysii.
- Marka xogta dhabta ah la xiro, **ka saar calaamadaha TUSAALE iyo digniinta kore** qaybaha dhabta ah, si booqdayaasha loo marin habaabin.

## Mashruuc taageere

Kuma xirna horyaal, koox ama xiriir kubadeed. Magacyada kooxaha waxaa loo adeegsadaa aqoonsi oo keliya.
