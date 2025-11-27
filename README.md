# 🏀 Basketball Score App  
### Proyecto Final – 1.º Trimestre  
**Autor:** Alberto Agredano

Aplicación Android desarrollada para gestionar el marcador de un partido de baloncesto en tiempo real. Este proyecto integra los conceptos principales vistos durante el trimestre: Views, Layouts, Intents, Data Binding y el uso adecuado de recursos Android.

---

## 📌 Descripción General

Basketball Score App permite al usuario aumentar o disminuir la puntuación de dos equipos (Local y Visitante), reiniciar el marcador y visualizar el resultado final en una segunda pantalla. El objetivo es ofrecer una experiencia sencilla, clara y práctica para el seguimiento de un partido.

---

## ✥ Funcionalidades

- Control de marcador para ambos equipos  
- Botones para sumar +1 y +2 puntos  
- Botón para restar puntos evitando valores negativos  
- Botón de reinicio para devolver el marcador a 0  
- Navegación hacia una pantalla de resultado final  
- Cálculo automático del ganador o empate  
- Uso de Intent.putExtra para enviar datos entre activities  
- Implementación completa de Data Binding  
- Gestión centralizada de textos con strings.xml  

---

## 🧱 Arquitectura de la Aplicación

### MainActivity
- Muestra los marcadores de ambos equipos  
- Permite modificar la puntuación  
- Incluye el botón de reinicio  
- Incluye el botón para navegar a ScoreActivity  
- Valida que la puntuación nunca sea negativa  

### ScoreActivity
- Recibe los valores enviados desde MainActivity  
- Muestra el marcador en formato X - Y  
- Determina el resultado final (Local, Visitante o Empate)  
- Presenta un mensaje contextual según el resultado  

---

## 🔗 Transferencia de Datos entre Activities

Envío de datos:

Intent intent = new Intent(this, ScoreActivity.class);
intent.putExtra(LOCAL_SCORE_KEY, localScore);
intent.putExtra(VISITOR_SCORE_KEY, visitorScore);
startActivity(intent);

Recepción de los datos:

int localScore = getIntent().getIntExtra(LOCAL_SCORE_KEY, 0);
int visitorScore = getIntent().getIntExtra(VISITOR_SCORE_KEY, 0);

---

## 🔧 Implementación de Data Binding

ActivityMainBinding binding = ActivityMainBinding.inflate(getLayoutInflater());
setContentView(binding.getRoot());

Beneficios:
- Eliminación de findViewById  
- Mayor seguridad de tipos  
- Mejor legibilidad  
- Reducción de errores  

---

## 📁 Estructura del Proyecto

app/
 ├── java/com.example.basketballscore/
 │      ├── MainActivity.java
 │      └── ScoreActivity.java
 ├── res/
 │      ├── layout/activity_main.xml
 │      ├── layout/activity_score.xml
 │      ├── values/strings.xml
 │      ├── values/colors.xml
 │      └── values/dimens.xml
 └── AndroidManifest.xml

---

## 📘 Recursos Utilizados

- strings.xml → textos  
- colors.xml → paleta de colores  
- dimens.xml → tamaños, márgenes, paddings  
- drawable/ → iconos y elementos gráficos  

---

## 🧪 Validaciones y Casos Considerados

- La puntuación nunca puede ser negativa  
- Reset completo del marcador  
- Navegación controlada mediante botón  
- Cálculo correcto del ganador  
- Envío de datos seguro mediante constantes  
- Manejo de casos límite (empates, valores iniciales, etc.)  

---

## 🚀 Instalación y Ejecución

1. Clonar el repositorio  
2. Abrir en Android Studio  
3. Sincronizar Gradle  
4. Ejecutar en emulador o dispositivo físico  

---

## ✔️ Buenas Prácticas Aplicadas

- Nombres descriptivos y consistentes  
- Código limpio y organizado  
- Comentarios solo donde aportan valor  
- Uso de constantes en Intent.putExtra  
- Gestión ordenada de recursos Android  
- Separación clara entre lógica y presentación  

---

## 📄 Autor
**Alberto Agredano**
