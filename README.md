# Árbol de Decisión - Empresa de Telecomunicaciones

## Descripción General

Este proyecto implementa un algoritmo de árbol de decisión desde cero para predecir si un cliente de una empresa de telecomunicaciones aceptará una oferta de plan de datos móviles. El análisis se basa en un pequeño conjunto de datos de 10 clientes y utiliza cálculos de entropía y ganancia de información para determinar el mejor atributo para dividir los datos.

El notebook demuestra los conceptos fundamentales de la construcción de árboles de decisión, incluyendo:
- Cálculo de entropía para el conjunto de datos original
- Evaluación de diferentes atributos (edad, línea fija, uso de datos)
- Análisis de ganancia de información
- Construcción de un árbol de decisión simple

## Tabla de Contenidos

- [Descripción General](#descripción-general)
- [Conjunto de Datos](#conjunto-de-datos)
- [Requisitos](#requisitos)
- [Instalación](#instalación)
- [Uso](#uso)
- [Metodología](#metodología)
- [Resultados](#resultados)
- [Conclusiones](#conclusiones)
- [Autor](#autor)
- [Licencia](#licencia)

## Conjunto de Datos

El conjunto de datos consta de 10 registros de clientes con los siguientes atributos:

- **ID**: Identificador único para cada cliente
- **Edad**: Edad del cliente en años
- **Uso de Datos**: Uso mensual de datos en GB
- **Tiene Línea Fija**: Si el cliente tiene servicio de línea fija (Sí/No)
- **Aceptó Oferta**: Si el cliente aceptó la oferta de plan de datos móviles (Sí/No)

Los datos se proporcionan como una lista de diccionarios en el notebook y se convierten a un DataFrame de pandas para el análisis.

## Requisitos

- Python 3.x
- pandas
- matplotlib
- math (biblioteca integrada de Python)

## Instalación

1. Clona este repositorio:
   ```bash
   git clone https://github.com/tu-usuario/arbol-telecomunicaciones.git
   cd arbol-telecomunicaciones
   ```

2. Instala los paquetes requeridos:
   ```bash
   pip install pandas matplotlib
   ```

3. Inicia Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

4. Abre `arbol_telecomunicaciones_final.ipynb`

## Uso

1. Ejecuta las celdas del notebook de manera secuencial para ver el análisis completo.
2. El notebook incluye:
   - Carga y visualización de datos
   - Cálculos de entropía para el conjunto de datos original
   - Evaluación de atributos (edad, línea fija, uso de datos)
   - Análisis de ganancia de información
   - Construcción del árbol de decisión

El notebook es autocontenido e incluye todo el código y explicaciones necesarias.

## Metodología

### Cálculo de Entropía
La entropía del conjunto de datos original se calcula usando la fórmula:
```
H(S) = -∑(p_i * log₂(p_i))
```
donde p_i es la proporción de cada clase (aceptó/no aceptó).

### Evaluación de Atributos
Para cada atributo, los datos se dividen en subconjuntos y se calcula la entropía ponderada:
```
H_división = ∑((|S_v| / |S|) * H(S_v))
```
donde S_v es cada subconjunto creado por el atributo.

### Ganancia de Información
La ganancia de información para cada atributo se calcula como:
```
Ganancia = H(S) - H_división
```

El atributo con la mayor ganancia de información se selecciona como raíz del árbol de decisión.

## Resultados

El análisis muestra que el atributo "Tiene Línea Fija" proporciona una separación perfecta:

- **Resultados de Ganancia de Información**:
  - Tiene Línea Fija: 1.0 (ganancia perfecta)
  - Edad: 0.449
  - Uso de Datos: 0.6

- **Árbol de Decisión**:
  ```
  ¿Tiene Línea Fija?
  ├── Sí → Aceptó Oferta
  └── No → No Aceptó Oferta
  ```

- **Precisión**: 100% (10/10 casos clasificados correctamente)

## Conclusiones

El atributo "Tiene Línea Fija" separa perfectamente las clases, creando dos subconjuntos puros con entropía cero. Esto resulta en un árbol de decisión simple y altamente interpretable que logra una clasificación perfecta en el conjunto de datos dado.

Este ejemplo demuestra un caso ideal donde un solo atributo es suficiente para una clasificación completa, destacando el poder de la ganancia de información en la selección de características para árboles de decisión.

## Autor

### Lucas Nahuel Oviedo

- Institución: Instituto Superior de Formación Técnica N° 197
- Carrera: Técnicatura Superior en Ciencia de Datos e Inteligencia Artificial
- Cátedra: Procesamiento de Aprendizaje Automático
- Docente: Yanina Scudero
- Año: 2025

## Licencia
Este proyecto está bajo la Licencia MIT.