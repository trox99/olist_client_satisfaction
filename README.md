# Olist — Análisis Probabilístico de Experiencia del Cliente

**Problema de negocio:** como analista de datos de Olist, el mayor marketplace de e-commerce de Brasil,
identifico qué factores explican la satisfacción del cliente (reseñas) y el comportamiento de
vendedores, para priorizar inversiones operativas con evidencia estadística.

**Dataset:** [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
(Kaggle) — 9 CSVs relacionados con ~99,000 pedidos reales (2016–2018). El análisis final se hace sobre
95,824 pedidos entregados con reseña completa.

## Resumen de hallazgos

- El **tiempo de entrega** es el factor que más explica la satisfacción del cliente: un pedido que
  tarda más del promedio (12.5 días) casi duplica la probabilidad de una reseña de 1–2 estrellas
  (20.4% vs. 8.2%). Invirtiendo esta relación con Bayes, **1 de cada 3 reseñas negativas** viene de un
  pedido tardío.
- El **método de pago** no explica el comportamiento de compra: aunque su asociación con la categoría
  de producto es estadísticamente significativa (χ²=822.75, p<0.001), el efecto real es prácticamente
  nulo (Cramer's V=0.054).
- Un modelo predictivo (regresión logística) confirma lo anterior: el tiempo de entrega es el
  predictor más fuerte de la reseña, por encima de precio o cuotas de pago.
- La categoría *telefonía fija* tiene el ticket de compra más volátil (CV=3.89); *tablets/impresión*,
  el más estable (CV=0.40).
- La experiencia del cliente en **Maranhão** diverge más del doble (KL=0.074 bits) frente a São Paulo
  que Río de Janeiro (KL=0.035 bits), lo que la señala como región prioritaria de intervención logística.

**Recomendación central:** invertir en estabilizar la logística de entrega, priorizando regiones de
mayor divergencia frente al mercado de referencia, antes que en ajustes sobre métodos de pago.
