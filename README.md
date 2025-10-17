# Aufgabe: Props kennenlernen

Wir wollen eine wiederverwendbare Card-Komponente bauen.
Diese Komponente nimmt zwei Props entgegen und zeigt verschiedene Inhalte an, je nachdem welche Props übergeben werden.
Die Karte soll einen Titel und

## Vorbereitung

```bash
npm create vite@latest aufgabe-react-props -- --template react-ts
cd aufgabe-react-props
npm install
npm run dev
```

Optional: Wähle die TypeScript-Variante

## Card Komponente

1. Erstelle einen neuen Ordner `/src/components`
2. Lege eine neue Datei `/src/components/Card.jsx` an

Vergiss nicht:

1. Functional Component erstellen
2. Props als Parameter entgegennehmen (title, description)
3. Props im JSX verwenden mit { }
4. TypeScript: Interface für Props definieren (optional aber empfohlen)
5. Component exportieren

## HTML/JSX Vorlage

Als Vorlage für das JSX kannst du diese Struktur benutzen:

```jsx
<div className="card">
    <h3>Titel</h3>
    <p>Beschreibung</p>
</div>
```

## TypeScript Props Interface (optional)

```tsx
interface CardProps {
    title: string;
    description: string;
}

function Card({ title, description }: CardProps) {
    // ...
}
```

## Verwendung in App.jsx

Binde die Card-Komponente mehrfach mit unterschiedlichen Props ein:

```tsx
import Card from "./components/Card";

function App() {
    return (
        <div>
            <h1>Meine Karten</h1>
            <Card
                title="React"
                description="Eine JavaScript Bibliothek für UI"
                imageUrl="https://via.placeholder.com/150"
            />
            <Card title="TypeScript" description="JavaScript mit Typen" imageUrl="https://via.placeholder.com/150" />
            <Card title="Vite" description="Schnelles Build Tool" imageUrl="https://via.placeholder.com/150" />
        </div>
    );
}
```

## Style

Erstelle eine Datei `/src/components/Card.module.css`:

```css
.card {
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 1rem;
    margin: 1rem;
    max-width: 300px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.card img {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-radius: 4px;
}

.card h3 {
    margin: 1rem 0 0.5rem 0;
    color: #333;
}

.card p {
    margin: 0;
    color: #666;
    line-height: 1.5;
}
```

Import in der Komponente:

```tsx
import styles from "./Drawer.module.css";
```

Verwendung:

```tsx
<div className={styles.drawer}>
```
