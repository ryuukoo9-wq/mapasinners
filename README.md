'# GTA V MAP LEAFLET 
GTA V MAP LEAFLET is a MAP  based on LEAFLET with authentication and point management.

## 🔐 Login

A senha padrão para acessar o mapa é: **3323030**

Você pode alterar a senha editando o arquivo `scripts/script.js` e mudando a constante:
```javascript
const SENHA_CORRETA = '3323030';
```

## Features

* Easy to use
* Custom Icons
* 3 Map Style(Atlas,Satellite,Grid)
* 🔐 Password authentication
* ⏱️ Timer system for Carros and ATMs
* 🎨 Dynamic color system (Green = Available, Red = Timeout)

## Dependencies
Map Styles
```
  https://mega.nz/file/UKo0wI4A#hDZV1RE-KU0rF2BePRjaKQfwWVBvWbsBVAFmM7yWvo8
```
Leaflet
```
 https://leafletjs.com/
```
## Install
```
  Extract map styles in source folder
```
## How to use
Create blip
The coordinates are inverted X will be Y and Y will be X.
```
var X  = 0;
var Y = 0;
L.marker([Y,X], {icon: customIcon(1)}).addTo(Icons["Example"]).bindPopup("I am here.");
```
How use CustomIcon
The parameter in the customIcon function is the name of the .png picture in the blips folder
```
For /blips/1.png we will use customIcon(1)}
```

## Cadastrar Pontos no Mapa

Existem duas formas de adicionar pontos ao mapa:

### 1. Clique Direito (Context Menu)
Clique com o botão direito em qualquer local do mapa para abrir um modal e cadastrar um ponto naquela localização.

### 2. Botão "Adicionar Coordenada"
Use o botão flutuante no canto inferior direito da tela para inserir coordenadas manualmente.

### Sistema de Temporizador

O temporizador é **independente** do ponto e pode ser editado a qualquer momento:

- **Verde 🟢**: Tempo = 0 (Ponto disponível)
- **Vermelho 🔴**: Tempo > 0 (Ponto em timeout/indisponível)

**Como funciona:**
1. Marque um ponto com tempo inicial (ex: 300 segundos)
2. Clique no marcador para ver o tempo restante
3. Clique em "✏️ Editar" para alterar o tempo manualmente
4. O marcador muda de cor conforme o tempo passa
5. Quando atinge 0, fica verde e disponível novamente

### Salvando Pontos Permanentemente
Os pontos devem ser adicionados ao arquivo `pontos.json` na raiz do projeto:

```json
{
  "pontos": [
    {
      "lat": 100,
      "lng": 100,
      "tipo": "Carro",
      "descricao": "Garagem Principal",
      "tempo": 300
    },
    {
      "lat": 150,
      "lng": 150,
      "tipo": "ATM",
      "descricao": "Caixa Eletrônico Downtown",
      "tempo": 600
    },
    {
      "lat": 80,
      "lng": 120,
      "tipo": "NPC",
      "descricao": "Vendedor de Armas"
    }
  ]
}
```

**Tipos disponíveis:** `Carro`, `ATM`, `NPC`

**Temporizador (opcional):** 
- Disponível para `Carro` e `ATM`
- Valor em segundos (ex: 300 = 5 minutos)
- Pode ser editado a qualquer momento clicando no ponto
- NPCs nunca têm timeout (sempre verde)
## Screenshots
| Atlas         |   Grid        |    Satellite    | 
| ------------- | ------------- | ----------------| 
| !["Atlas Screenshot"](https://cdn.discordapp.com/attachments/691276350962794496/908677027530407966/unknown.png)  | !["Grid Screebshot"](https://cdn.discordapp.com/attachments/691276350962794496/908677312109764608/unknown.png)  |    !["Satellite Screenshot"](https://cdn.discordapp.com/attachments/691276350962794496/908676688043454495/unknown.png)             | 

Custom blip
!["Customblip Screnshot"](https://cdn.discordapp.com/attachments/691276350962794496/908677500069109800/unknown.png)
## License

GTA V MAP LEAFLET is licensed under MIT License.
