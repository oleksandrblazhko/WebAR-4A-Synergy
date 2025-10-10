## Налаштування роздільної здатності
Додано можливість налаштовувати роздільну здатність веб-камери через конфігураційний файл `config.json`.

### Варіанти налаштувань:
- `"high"` - 1280x720 (висока роздільна здатність)
- `"low"` - 640x480 (низька роздільна здатність, за замовчуванням)

### Приклад налаштування:
```json
{
  "settings": {
    "resolution": "high"
  },

}
```

## Налаштування привітального тексту
Додано можливість налаштовувати привітальний текст, який відображається перед входом у WebAR-застосунок.

### Приклад налаштування:
```json
{
  "settings": {
    "welcomeText": "Press here<br>to enter the WebAR-Board Game"
  },
  ]
}
```

## Типи контенту
- `model` - складна 3D-модель
- `primitive` - примітивна 3D-модель
- `image` - зображення
- `video` - відео
- `controller` - інтерактивний контролер (зелений куб)

## Структура конфігурації маркерів
Кожен маркер має наступну структуру:
- `id` - унікальний ідентифікатор
- `type` - тип маркера ("pattern" або "barcode")
- `target` - шлях до файлу патерну або номер баркоду
- `contentType` - тип контенту
- Додаткові параметри залежно від типу контенту

# Приклади конфігурацій для типу "primitive"
Тип контенту `primitive` дозволяє створювати прості 3D-фігури без необхідності завантажувати зовнішні 3D-моделі.

## Підтримувані типи геометрій
- `BoxGeometry` - куб або прямокутний паралелепіпед
- `SphereGeometry` - сфера
- `CylinderGeometry` - циліндр
- `ConeGeometry` - конус
- `TorusGeometry` - тор (бублик)

## Параметри примітиву
- `type` - тип геометрії (BoxGeometry, SphereGeometry, CylinderGeometry, ConeGeometry, TorusGeometry)
- `size` - розміри для BoxGeometry [ширина, висота, глибина]
- `radius` - радіус для SphereGeometry, ConeGeometry, TorusGeometry
- `height` - висота для ConeGeometry, CylinderGeometry
- `tubeRadius` - радіус трубки для TorusGeometry
- `widthSegments`, `heightSegments` - сегменти для SphereGeometry
- `radiusTop`, `radiusBottom`, `radialSegments` - параметри для CylinderGeometry
- `tubularSegments` - сегменти трубки для TorusGeometry
- `color` - колір об'єкта (у форматі hex, наприклад "#ff0000")
- `textureFile` - шлях до текстурного файлу для застосування до поверхні (опційно)
- `position` - позиція об'єкта [x, y, z]
- `rotation` - обертання об'єкта [x, y, z] у радіанах
- `animation` - параметри анімації (опційно)

## Анімація для примітивів та 3D-моделей
Тепер підтримується анімація обертання як для примітивів, так і для 3D-моделей з наступними параметрами:

- `type` - тип анімації ("rotation")
- `axis` - вісь обертання ("x", "y" або "z")
- `speed` - швидкість обертання (числове значення)


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
