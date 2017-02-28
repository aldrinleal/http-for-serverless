class: center, middle

# Hospedaje Estática de Aplicaciones Serverless

Aldrin Leal, &lt;aldrin@leal.eng.br&gt;

---

# Agenda

 * Yo?
 * Objectivos
 * Visión General de HTTP
 * Aspectos de Performance y Seguridad
 * Hospedaje Serverless
 * Conclusiones

---

# Yo?

 * Paisa
 * Foco actual: AWS y Big Data
 * Hobby: Devops y sus Herramientas 

---

# Objectivos

 * Comprender los principales aspectos de hospedaje de sitios HTTP estáticos
 * Presentar problemas y soluciones posibles

---

# Visión General de HTTP

 * TBL/CERN/Mosaic: HTTP 1.0
 * HTTP 1.1:
   * Hospedaje Multiple
   * Pipelining
 * TLS:
   * Limitante: 1 Certificado por IP
   * SNI
 * SDPY / HTTP 2.0: Binario
   * TLS Involucrado
 * Métodos Restful: GET DELETE PUT POST OPTIONS HEAD PATCH

---

# Ciclo de Vida de una Requisicion HTTP

  * 1.1:
    * DNS
    * Conexion / Negociacion TLS
    * Requisicion
    * Mime Type / Rendering
    * Recursos Auxiliares (max 4 p/ host)
      * CDNs

---

# Ciclo de Vida de una Requisicion HTTP 2

  * 2.0:
    * Casi lo mismo, excepto que no hay mas limitaciones de paginas por host

  * Impacto imediato: CDN y Minifiers

---

# Anatomia de una Conexion HTTP 1.0

  * Host
  * Accept
    * Idioma
  * Rangos de Transferência
  * Content-Type
  * Tipos MIME
    * Codificación

---

# Performance

  * DNS
    * A vs CNAME: "Naked" Domains
  * CDNs
    * CloudFront
    * Akamai
    * CloudFlare
    * Otros

---

# Seguridad

  * TLS
    * Letsencrypt
    * ACM
  * XSS: CORS
    * Headers de Resposta
    * Metodo HTTP Options

---

# Utilizando HTTP Local

  * caddy
  * ngrok

---

# Y En Nube?

  * Github? Sisas parce
  * VPS: 2 horas, custo mensual, sin escalar
  * S3 vs Firebase

---

# Evaluando algunos exemplos

  * Esta presentacion en github
  * 

---

# Y serverless?

  * Puedes usar qualquier cosa, como:
    * Generadores Estaticos (Hugo, Jekyll)
    * HTML + CSS + JS
      * SVG: Perigo con tipos Mime
    * Notepad :)
    * HubPress
  * Pero si quieres APIs, piensa en FaaS:
    * Lambda / API Gateway / Cognito (Auth0?)
  * No te olvides de CORS

---

# Quiero criar mi (landing page | portafolio | sitio estatico)?

  * Interesante tener algun control de version (e.g. git)
    * Algunos son solamente escrita
  * Obviamente, contenido pero tambien transacionales
    * Disqus / Otras herramientas para comentarios

---

# Obrigado!

> aldrin@leal.eng.br / https://about.me/aldrinleal
