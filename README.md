# AstroLab WebApp

App web para estudos astrofísicos com:
- simulação física no navegador
- exportação CSV
- exportação GLTF
- exportação de vídeo do canvas via MediaRecorder
- exportação GIF via gif.js (CDN)
- integração com JPL Horizons por proxy local

## Observações importantes
- A API do JPL SSD/Horizons informa que **não pode ser embutida diretamente em sites**, por política de CORS; por isso este projeto usa um **proxy backend** local. (documentação oficial)
- Gravação em **MP4 no navegador não é garantida**. O MediaRecorder permite pedir `video/mp4`, mas o formato escolhido depende do navegador; `video/webm` costuma ser mais confiável. Verifique com `MediaRecorder.isTypeSupported()`. (MDN)
- Eu não consigo hospedar este app publicamente a partir daqui.

## Rodando localmente

### Backend
```bash
cd server
npm install
npm start
```

### Frontend
Abra `public/index.html` em um servidor estático local, por exemplo:
```bash
cd public
python -m http.server 8000
```
Acesse `http://localhost:8000`.

O frontend espera o proxy em `http://localhost:8787`.
