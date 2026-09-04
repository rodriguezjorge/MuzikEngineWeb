# Publicar Muzik Engine Band en GitHub Pages

Mismos pasos que se usaron para MedanosWeb (`github.com/rodriguezjorge/MedanosWeb`).

## 1. Crear el repositorio en GitHub

1. Entra a **https://github.com/new** (ya con tu sesión de `rodriguezjorge` iniciada).
2. **Repository name:** `MuzikEngineWeb`
3. Visibility: **Public**
4. **No** marques "Add a README" (ya existe uno local).
5. Clic en **Create repository**.

## 2. Subir el código local

Desde esta carpeta (`MuzikEngineWeb`), en una terminal:

```bash
git init
git add .
git commit -m "Muzik Engine Band: sitio prototipo inicial"
git branch -M main
git remote add origin https://github.com/rodriguezjorge/MuzikEngineWeb.git
git push -u origin main
```

Git te pedirá iniciar sesión en GitHub la primera vez (se abre el navegador o pide usuario/token).

## 3. Activar GitHub Pages

1. En el repo: **Settings** → **Pages** (menú izquierdo).
2. **Build and deployment** → **Source:** Deploy from a branch.
3. **Branch:** `main` · **Folder:** `/ (root)`.
4. **Save**.
5. En 1–2 minutos el sitio estará en:
   **https://rodriguezjorge.github.io/MuzikEngineWeb/**

Cada `git push` a `main` actualiza el sitio automáticamente.

## 4. Dominio propio (opcional)

Igual que en [MedanosWeb/DOMINIO-Y-HOSTING.md](../MedanosWeb/DOMINIO-Y-HOSTING.md): comprar un
dominio (ej. `muzikengineband.com`) y apuntarlo con registros **A** a las IPs de GitHub Pages:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

o un **CNAME** a `rodriguezjorge.github.io` para un subdominio como `www.muzikengineband.com`.
Luego agrega el dominio en **Settings → Pages → Custom domain** (esto crea el archivo `CNAME`
automáticamente).
