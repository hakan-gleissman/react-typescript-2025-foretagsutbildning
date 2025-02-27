---
theme: default
marp: true
---

# Övning: Implementera React Router med två routes

**Mål:**  
Att integrera React Router i din applikation genom att skapa två sidor (LoginPage och Dashboard) och definiera navigering via en onClick-händelse på en knapp.

---

# Steg 1: Installera React Router

1. Öppna terminalen i din projektmapp.
2. Kör kommandot:

```bash
npm install react-router-dom
```

---

# Steg 2: Skapa LoginPage

- Skapa fil: `src/components/LoginPage.tsx`.
- Importera useNavigate:
```javascript
import { useNavigate } from "react-router-dom";
```
- Skapa komponenten LoginPage: `const LoginPage = () => {}`
- Skapa ett handtag till `useNavigate` i komponenten:
```javascript
const navigate = useNavigate();
```
---

- I LoginPage ska du ha följande jsx:

  - Skapa `<div>`-element som omsluter två HTML `<input>`-fält:
    - Ett `<input type="text">` för användarnamn.
    - Ett `<input type="password">` för lösenord.
    - En knapp för att logga in
  - Så här:

    ```html
    return (
      <div>
        <input type="text" placeholder="Användarnamn" />
      </div>
      <div>
        <input type="password" placeholder="Lösenord" />
      </div>
      <button onClick={handleLogin}>Logga in</button>
    )
    ```

---

# Skapa on-click-funktionen handleLogin

- Knappen ska ha en onClick-funktion som använder React Router's `useNavigate` för att navigera till Dashboard-sidan.

```typescript
const handleLogin = () => {
  navigate("/dashboard");
};

```

---

# Steg 3: Skapa Dashboard

- Skapa en fil: `src/components/Dashboard.tsx`.
- Dashboard ska innehålla:

  - En rubrik, t.ex. `<h1>Dashboard</h1>`.
  - Två navigationslänkar som pekar till:
    - `/movies`
    - `/register-movie`
  - Dessa länkar skapas med React Router's `Link`-komponent, t.ex:

  ```typescript
  <Link to="/movies">Visa filmer</Link>
  ```

  - En logout-knapp (kan vara en enkel knapp utan funktion just nu).

---

# Steg 4: Integrera React Router i App-komponenten

- Öppna `src/App.tsx`.
- Importera BrowserRouter, Routes, och Route från `react-router-dom`.
- Omslut hela applikationen med `<BrowserRouter>`.
- Mellan Header och Footer, skapa ett `<main>`-element. Syftet med `<main>` är att definiera huvudinnehållet (där rutter renderas).
- Inom `<main>`, definiera dina rutter med `<Routes>`:
  - En route med `path="/"` som renderar LoginPage.
  - En route med `path="/dashboard"` som renderar Dashboard.
    Ex på hur det ser ut på nästa sida:

---

```typescript
const App = () => {
  return (
    <BrowserRouter>
      <div className={`container-fluid ${styles.fullSize}`}>
        //Header här
        <main>
          <Routes>
            <Route path="/" element={<LoginPage />} />
            <Route path="/dashboard" element={<Dashboard />} />
          </Routes>
        </main>
        //Footer här
      </div>
    </BrowserRouter>
  );
};
```
