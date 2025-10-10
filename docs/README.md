# Приклади конфігурацій для типу "primitive"

## Куб з текстурою та анімацією обертання (замінив відео на маркері з ID 5)
```json
{
  "id": 5,
  "type": "barcode",
  "target": 3,
  "contentType": "primitive",
  "primitive": {
    "type": "BoxGeometry",
    "size": [1, 1, 1],
    "color": "#ff0000",
    "textureFile": "data/texture.jpg",
    "position": [0, 0, 0],
    "rotation": [0, 0, 0],
    "animation": { "type": "rotation", "axis": "y", "speed": 0.01 }
  }
}
```

## Сфера з текстурою та анімацією обертання (замінив відео на маркері з ID 7)
```json
{
  "id": 7,
  "type": "barcode",
  "target": 4,
  "contentType": "primitive",
  "primitive": {
    "type": "SphereGeometry",
    "radius": 0.5,
    "widthSegments": 16,
    "heightSegments": 16,
    "color": "#00ff00",
    "textureFile": "data/checkerboard.png",
    "position": [0, 0, 0],
    "rotation": [0, 0, 0],
    "animation": { "type": "rotation", "axis": "x", "speed": 0.02 }
  }
}
```

## Циліндр з текстурою та анімацією обертання (замінив відео на маркері з ID 9)
```json
{
  "id": 9,
  "type": "barcode",
  "target": 5,
  "contentType": "primitive",
  "primitive": {
    "type": "CylinderGeometry",
    "radiusTop": 0.3,
    "radiusBottom": 0.3,
    "height": 1,
    "radialSegments": 16,
    "color": "#0000ff",
    "textureFile": "data/stripes.jpg",
    "position": [0, 0, 0],
    "rotation": [0, 0, 0],
    "animation": { "type": "rotation", "axis": "z", "speed": 0.015 }
  }
}
```

## Конус з текстурою та анімацією обертання (новий маркер з ID 11)
```json
{
  "id": 11,
  "type": "barcode",
  "target": 6,
  "contentType": "primitive",
  "primitive": {
    "type": "ConeGeometry",
    "radius": 0.5,
    "height": 1,
    "radialSegments": 16,
    "color": "#ffff00",
    "textureFile": "data/cone_texture.jpg",
    "position": [0, 0, 0],
    "rotation": [0, 0, 0],
    "animation": { "type": "rotation", "axis": "y", "speed": 0.01 }
  }
}
```

## Тор з текстурою та анімацією обертання (новий маркер з ID 12)
```json
{
  "id": 12,
  "type": "barcode",
  "target": 7,
  "contentType": "primitive",
  "primitive": {
    "type": "TorusGeometry",
    "radius": 0.5,
    "tubeRadius": 0.2,
    "radialSegments": 16,
    "tubularSegments": 32,
    "color": "#ff00ff",
    "textureFile": "data/torus_texture.jpg",
    "position": [0, 0, 0],
    "rotation": [0, 0, 0],
    "animation": { "type": "rotation", "axis": "x", "speed": 0.02 }
  }
}
```

## Великий куб без анімації (замінив відео на маркері з ID 13)
```json
{
  "id": 13,
  "type": "barcode",
  "target": 8,
  "contentType": "primitive",
  "primitive": {
    "type": "BoxGeometry",
    "size": [2, 0.5, 1],
    "color": "#ffff00",
    "textureFile": "data/checkerboard.png",
    "position": [0, 0, 0],
    "rotation": [0.5, 0.5, 0]
  }
}
```

## Сфера з повільною анімацією обертання (замінив відео на маркері з ID 14)
```json
{
  "id": 14,
  "type": "barcode",
  "target": 9,
  "contentType": "primitive",
  "primitive": {
    "type": "SphereGeometry",
    "radius": 0.7,
    "widthSegments": 24,
    "heightSegments": 24,
    "color": "#ff00ff",
    "textureFile": "data/gradient.jpg",
    "position": [1, 0, 0],
    "rotation": [0, 0.5, 0],
    "animation": { "type": "rotation", "axis": "z", "speed": 0.005 }
  }
}
```
