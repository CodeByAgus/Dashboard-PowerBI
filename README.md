# 📊 Dashboard: Servicios Básicos en Barrios Populares (RENABAP 2023)

## 🌟 Resumen del Proyecto

Este repositorio contiene el proyecto y la documentación de un dashboard interactivo enfocado en el **estado de los servicios básicos** (cloacas, electricidad, calefacción, cocina y agua) en los **Barrios Populares** de Argentina, con datos basados en el **RENABAP 2023**.

El objetivo principal es visualizar y analizar la criticidad de la provisión de servicios por barrio y provincia, y el estado de la situación dominial.

---

## 🖼️ Vistas Previas del Dashboard

### Vista del Modelo de Datos (Esquema de Tablas)

![Modelo de datos del dashboard](https://github.com/CodeByAgus/Dashboard-PowerBI/raw/3113b6abcc184058abd3f2c92496e05f1132bb6f/Captura%20de%20pantalla%202025-11-03%20001646.png)

### Dashboard en Acción (Demostración de Interacción)

![Demostración interactiva del dashboard](https://github.com/CodeByAgus/Dashboard-PowerBI/raw/b93e5f5accf3f4cda7163cd61ca5a8833319abcf/Dashboard%20interactuando.gif)
---

## 🔑 Características Principales

* **Análisis de Criticidad de Servicios:** Evaluación detallada del porcentaje de deficiencia/criticidad en los servicios de cloacas, electricidad, calefacción, cocina y agua.
* **Distribución Geográfica:** Visualización de la cantidad de barrios y familias por provincia (Buenos Aires, Córdoba, Santa Fe, etc.).
* **Situación Dominial:** Resumen de la tenencia (Asentamiento, Villa, Conjunto habitacional degradado) y el porcentaje de inseguridad dominial.
* **Top 5 Provincias:** Ranking de provincias con mayor cantidad de familias en Barrios Populares.

---

## 💾 Estructura de Datos (Modelo Lógico)

El dashboard utiliza un modelo de datos robusto para cruzar información geográfica y de servicios. La estructura central gira en torno a la tabla de **Datos Barrios Populares**, que se relaciona con las diferentes dimensiones de servicio y criticidad.

| Tabla | Descripción | Relaciones Clave |
| :--- | :--- | :--- |
| **Datos Barrios Populares** | Contiene información central sobre cada barrio: ubicación, familias aproximadas, situación dominial. | Es la tabla *hecho* central del modelo. |
| **Situación Dominial** | Clasificación de la tenencia (ej: Asentamiento, Villa). | 1:N con `Datos Barrios Populares`. |
| **Agua corriente** | Detalle de la provisión y el estado (Eficiente, Deficiente, Crítica). | N:1 con `Datos Barrios Populares`. |
| **Energía eléctrica** | Detalle de la conexión y el estado (Eficiente, Deficiente, Crítica). | N:1 con `Datos Barrios Populares`. |
| **Gas Natural-Calefaccion** | Detalle de la fuente de calefacción. | N:1 con `Datos Barrios Populares`. |
| **Gas Natural-Cocina** | Detalle de la fuente de gas para la cocina. | N:1 con `Datos Barrios Populares`. |
| **Efluentes cloacales** | Detalle de la provisión de cloacas y el estado (Eficiente, Deficiente, Crítica). | N:1 con `Datos Barrios Populares`. |
| **Nivel de Criticidad** | Tabla de apoyo para ordenar y clasificar los niveles de servicio (Crítica, Deficiente, Eficiente). | N:1 con las tablas de servicio. |
| **Medio de Servicio** | Dimensión auxiliar para los parámetros de servicio. | N:1 con `Datos Barrios Populares`. |
