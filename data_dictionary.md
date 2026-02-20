# Data Dictionary — Proyecto original

Este documento describe las columnas principales del dataset **china_cancer_patients_synthetic_Grupo1.xlsx** tal como aparece en el proyecto original. Ajusta nombres si tu archivo tiene variaciones.

## Columnas principales
- **PatientID**: Identificador único del paciente (string).
- **Gender**: Género del paciente (Male / Female / Other).
- **Age**: Edad en años (int).
- **Province**: Provincia o región de residencia (string).
- **Ethnicity**: Etnicidad o grupo poblacional (string).
- **TumorType**: Tipo de tumor o diagnóstico (string).
- **CancerStage**: Etapa del cáncer (I, II, III, IV o similar) (string).
- **DiagnosisDate**: Fecha de diagnóstico (datetime).
- **TumorSize**: Tamaño del tumor (unidad según origen del dataset; float).
- **Metastasis**: Indica presencia de metástasis (Yes / No / Unknown) (string).
- **TreatmentType**: Tipo de tratamiento principal (surgery, chemo, radio, etc.) (string).
- **SurgeryDate**: Fecha de cirugía (datetime).
- **ChemotherapySessions**: Número de sesiones de quimioterapia (int).
- **RadiationSessions**: Número de sesiones de radioterapia (int).
- **SurvivalStatus**: Estado de supervivencia (Alive / Deceased / Unknown) (string).
- **FollowUpMonths**: Meses de seguimiento desde el diagnóstico (int).
- **SmokingStatus**: Historial de tabaquismo (Yes / No / Former) (string).
- **AlcoholUse**: Consumo de alcohol (Yes / No / Occasional) (string).
- **GeneticMutation**: Mutación genética identificada (si aplica) (string).
- **Comorbidities**: Comorbilidades listadas (string; múltiples separadas por `;` o `,`).

## Columnas derivadas recomendadas (sugeridas para el pipeline)
- **Total_Treatment**: Suma de sesiones de quimioterapia y radioterapia (int).
- **Ratio_Tumor_Age**: `TumorSize / Age` (float).
- **SurgeryDate_missing**: Flag 0/1 indicando si falta `SurgeryDate`.
- **GeneticMutation_missing**: Flag 0/1 indicando si falta `GeneticMutation`.
- **Comorbidities_missing**: Flag 0/1 indicando si falta `Comorbidities`.

## Notas sobre calidad y formato
- **Fechas**: normalizar a formato ISO (`YYYY-MM-DD`) y convertir a `datetime` para análisis temporal.
- **Nulos**: documentar la estrategia (ej. imputación, eliminación o flags de missing).
- **Unidades**: confirmar unidad de `TumorSize` (mm, cm) y documentarla.
- **Valores categóricos**: estandarizar categorías (ej. `Male`/`Female` en lugar de `M`/`F`).
- **Comorbilidades**: si están en una sola celda separadas por delimitador, normalizar a lista o tabla auxiliar para análisis por comorbilidad.
- **Privacidad**: si el dataset contiene información sensible, anonimizar `PatientID` y cualquier identificador personal antes de publicar.

## Recomendación rápida
Mantener este archivo actualizado con cualquier cambio en nombres de columnas o nuevas variables derivadas; incluir en README para entendimiento del esquema
