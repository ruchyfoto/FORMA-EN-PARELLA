# Forma en Parella

Aplicació web per entrenar en parella: calendari de 6 dies d'exercici i 1 de descans (que pots moure cada setmana), variants de gimnàs i de casa amb dibuixos, cronòmetre, dieta segons el pes i seguiment del progrés. Les dades de les dues persones es sincronitzen entre dispositius amb un codi de parella.

## Contingut

- `index.html`: tota l'aplicació en un sol fitxer.
- `netlify/functions/sync.mjs`: la petita funció que desa i combina les dades (Netlify Blobs).
- `netlify.toml` i `package.json`: configuració de Netlify.

## 1. Pujar-ho a GitHub

1. Crea un repositori nou a github.com (per exemple `forma-en-parella`). Deixa'l **privat**.
2. A la carpeta del projecte, executa:

```bash
git init
git add .
git commit -m "Forma en Parella"
git branch -M main
git remote add origin https://github.com/EL_TEU_USUARI/forma-en-parella.git
git push -u origin main
```

Si no vols fer servir el terminal, al repositori nou toca **uploading an existing file** i arrossega tots els fitxers i la carpeta `netlify`.

## 2. Publicar-ho a Netlify

1. A app.netlify.com, **Add new site → Import an existing project → GitHub** i tria el repositori.
2. No cal canviar res: Netlify llegeix `netlify.toml`. Prem **Deploy**.
3. Quan acabi, tens una adreça tipus `https://nom-aleatori.netlify.app`. Pots canviar el nom a **Site configuration → Change site name**.

No cal cap variable d'entorn ni cap base de dades: l'emmagatzematge (Netlify Blobs) ve inclòs.

## 3. Sincronitzar els dos mòbils i ordinadors

1. Obre l'adreça de Netlify al primer dispositiu. Ves a **Perfil → Sincronitzar dispositius** i prem **Generar codi nou**, després **Connectar**.
2. Copia el codi i escriu-lo igual al dispositiu de la teva parella (i als altres dispositius vostres).
3. A dalt de tot de l'aplicació, cadascú tria el seu perfil. Cada perfil guarda les seves dades a part, així que podeu entrenar a la vegada.

Notes:
- El codi és la clau: qui el tingui pot veure i canviar les vostres dades. Guarda'l només per a vosaltres dos.
- Si dues persones canvien el mateix perfil a la vegada, es queda l'últim canvi.
- A l'iPhone: Compartir → **Afegir a la pantalla d'inici**. A Android: menú → **Instal·lar aplicació**.
- Cada canvi es puja uns segons després, i l'aplicació consulta les novetats cada 30 segons.

## Provar-ho en local

```bash
npm install -g netlify-cli
npm install
netlify dev
```
