Deep Research

Ek chhota tool jo kisi sawaal ka web se jawab dhoondhta hai, sources padhta hai, aur har claim ke saath source ke saath report deta hai.

Maine ye isliye banaya kyunki research mein sabse mushkil kaam sources par bharosa karna aur hazaar pages se summary banana hota hai. Ye tool us kaam ka pehla draft hai, perfect nahi.

Kyun banaya

Mere internship ke dauran aur college research mein ek hi pattern baar-baar dikha: pehle 10 tabs khulte hain, phir ghanton mein notes bante hain, aur phir bhi ye nahi pata hota ki ek line kis page se aayi. Isliye maine focus kiya traceability par. Har point ke saath URL hai, taaki koi bhi claim ek click mein check ho sake.

Kaise kaam karta hai

1. Sawaal ko English search keywords mein badalta hai (search engines English par behtar chalte hain).
2. Use 3 chhote sub-questions mein todta hai.
3. Har sub-question ke liye DuckDuckGo search karta hai.
4. Pages ka text nikaalta hai, aur sirf wahi lete hain jisme kaafi content ho.
5. Har page se 2-3 points nikaalta hai, jinmein model ko sirf wahi likhne ko kaha gaya hai jo page mein likha ho. Jahan jaankari nahi, wahan NO_INFO ho jata hai aur wo page drop ho jata hai.
6. Bache hue notes se final report banta hai, jisme sources bhi hote hain.

Design decisions aur tradeoffs

- Free model kyun: Groq ka free tier. Cost zero rakhna isliye zaroori tha ki ye ek personal project hai. Tradeoff: accuracy paid models se kam hai.
- Reasoning models skip kiye: Testing mein gpt-oss jaise models ne max_tokens reasoning mein khatam karke khaali jawab diya. Isliye unhe model selection se bahar rakha.
- Pages kam rakhe (default 2 per sub-question): Speed aur depth ka balance. Settings se badal sakte ho.
- NO_INFO filter: Model ke galat ya bana hua content ko kam karne ka sabse simple tareeka. Ye pura fix nahi hai, par hallucination kam karta hai.
- Password lock: Public deploy par Groq quota koi aur na use kare, isliye.

Known limitations (ye khud pata hain)

- Local ya free model ka reasoning kamzor hai. Ek-do facts galat aa sakte hain, isliye original link check karna zaroori hai.
- DuckDuckGo kabhi irrelevant pages deta hai. Abhi koi relevance scoring nahi hai.
- Devanagari PDF mein nahi dikhti (Arial font mein glyphs nahi).
- Cloud par history aur PDFs restart par reset ho sakti hain.

Agle kadam

- Relevance check (page ka title aur query ka match) add karna.
- Claim-level verification: har point ko uske source se match karna.
- Har report ka quality score (kitne sources se claim verify hua).

Setup

pip install -r requirements.txt
set GROQ_API_KEY=your_key
streamlit run app.py

Deploy ke liye Streamlit Community Cloud par GROQ_API_KEY aur APP_PASSWORD secrets mein daalo.
