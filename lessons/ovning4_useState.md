---
theme: default
marp: true
---

# Övning: Like Button-komponent med React Icons och useState

**Uppgift:**

- Skapa en komponent som visar en "like"-knapp.
- När knappen klickas ska en räknare (like count) öka med 1.
- Använd React Icons för att visa en ikon (t.ex. en hjärtaikon).
- Använd `useState`-hooken för att hantera räknarens state.

---

# Steg 1: Installera React Icons

- Öppna terminalen i din projektmapp.
- Kör följande kommando för att installera react-icons:

```bash
npm install react-icons
```

---

# Steg 2: Skapa LikeButton-komponenten

1. Skapa en ny fil `src/components/LikeButton.tsx`.
2. Importera useState från React.
3. Importera en ikon från react-icons (t.ex. `FaHeart` från `react-icons/fa`).

```typescript
import { FaHeart } from "react-icons/fa";
```

4. Skapa komponenten med en state-variabel för räknaren (exempelvis `likes`) och en funktion för att öka den.
5. Returnera ett `<button>`-element som innehåller ikonen och räknaren. När knappen klickas, ska räknaren öka med 1:

```typescript
<button className="btn btn-outline-primary" /*onclick-handler*/>
  <FaHeart /> {likes}
</button>
```

---

# Integration i App-komponenten

**Instruktioner:**

- Importera LikeButton-komponenten.
- Lägg LikeButton någonstans i din layout, exempelvis i Footer, innan CompanyInfo.

