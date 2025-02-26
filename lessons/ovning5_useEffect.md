---
theme: default
marp: true
---

# Övning: DataList-komponent – Hämta Användardata från API med useEffect

---
1. **Skapa DataList-komponenten:**  
   - Skapa en fil `src/components/DataList.tsx`.
   - Importera `useEffect` och `useState` från React.
---
2. **Definiera User-datatypen:**  
   - Skapa i `DataList.tsx` en typ med namnet `User` som representerar ett objekt från API:et.
   - API:et (`https://jsonplaceholder.typicode.com/users`) returnerar användardata med flera fält. Några exempelvärden du kan använda i din typ:
     - `id`: number  
     - `name`: string  
     - `username`: string  
     - `email`: string  
   - Du kan välja att inkludera de fält du anser mest relevanta, exempelvis `id` och `name`.
---

2. **Skapa DataList-komponenten:**  
   - Använd useState för att lagra en array med användare, med typen `User[]`.
   - Använd useEffect (med en tom dependencies-array) för att hämta data från API:et när komponenten mountas.
   - Ta emot svaret från API:et, konvertera det till JSON och spara resultatet i state.  
---  

3. **Rendera HTML-lista med jsx:**  
   - Använd ett `<ul>`-element för att skapa en lista.
   - Mappa arrayen med Users och rendera ett `<li>`-element för varje användare. Varje `<li>` ska visa användarens namn (använd fältet `name` från din User-typ).
   - Se till att varje `<li>` har ett unikt `key`-attribut (t.ex. använd `user.id`). Så här kan de se ut:
```typescript
return (
    <ul>
      {users.map((user) => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
```
---

4. **Integrera i App-komponenten:**  
   - Importera DataList-komponenten i `src/App.tsx`.
   - Placera DataList-komponenten mellan din Header och Footer så att den visas som huvudinnehåll.

---


