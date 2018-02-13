# Balboa Coin
#### ANTEPROYECTO
#### Autores
* 	*Aldo Antinori*
* 	*Ira Miller public@iramiller.com*
#### Licencia
*CC-BY-4.0*
### PROPÓSITO
En este documento se presenta la sección del dólar digital del Plan Estratégico de Panama Glass. Los autores no lo exponen como una plataforma política, sino simplemente lo proponen como un posible camino a considerar. Es un documento "vivo" que es actualizado antes y durante la cumbre de Panama Glass, por los organizadores, oradores y estudiantes asistentes.
### RESUMEN
Balboa Coin (abreviado [XBC] [1](https://www.iso.org/iso-4217-currency-codes.html "ISO 4217 requires X before non-country codes, like XAU for gold")) es una ficha digital que capta el valor de la infraestructura comercial como canales, carreteras y puertos. Aunque el plan a largo plazo es extraer y ampliar para abarcar una región más grande, este documento propondrá un modelo inicial con solo Panamá y el Canal de Panamá.
Al implementar una ficha digital para el acceso al Canal de Panamá, los administradores del canal podrían ahorrar decenas de millones de dólares al año en tarifas, reinvertir una gran parte de las ganancias y pagar dividendos a cada panameño. Los panameños recibirían un ingreso básico universal y servicios bancarios universales en sus teléfonos celulares. Balboa Coin le proporcionará al expendedor un descuento y otras ventajas cuando pague para el acceso al Canal, incentivando el uso de las compañías navieras.
## Implementación
### Distribución de Clave
Se requeriría que cada ciudadano panameño registre una clave de firma oficial [RSA] [2](http://people.csail.mit.edu/rivest/Rsapaper.pdf "R.L. Rivest, A. Shamir, and L. Adleman “A Method for Obtaining Digital Signatures and Public-Key Cryptosystems") con el Tribunal Electoral. Las empresas de telecomunicaciones también podrían ser delegadas como agentes para esta actividad, requiriendo un número de cedula único para cada tarjeta sim activada para Balboa Coin.
Esto es similar a la forma en que Estonia emite identificaciones digitales como parte de su [programa de residencia electrónica] [3](https://e-resident.gov.ee/). Al igual que Estonia, estas claves podrían integrarse en un chip compatible con [openPGP] [4](https://tools.ietf.org/html/rfc4880 "RFC 4880 “OpenPGP Message Format”") dentro de la cédula, o podría hacerse un chip por separado en una tarjeta inteligente, USB o diseño de tarjeta SIM.
Estonia no fue tan diligente y usó versiones antiguas, [implementaciones no estándares] [5](https://csrc.nist.gov/publications/detail/sp/800-131a/archive/2011-01-13 "NIST SP800-131A “Transitions: Recommendation for Transitioning the Use of Cryptographic Algorithms and Key Lengths”, 2011") en sus tarjetas. Específicamente, sus claves RSA eran solo de 1024 bits, mientras que nosotros recomendaríamos claves de 4096 bits. A raíz de esta implementación deficiente, se identificó [una debilidad] [6]( https://crocs.fi.muni.cz/_media/public/papers/nemec_roca_ccs17_preprint.pdf "Matus Nemec, Marek Sys, Petr Svenda, Dusan Klinec, Vashek Matyas “The Return of Coppersmith’s Attack: Practical Factorization of Widely Used RSA Moduli") en el 2017. Esto no dañó instantáneamente todas las claves, pero requirió que Estonia congelara el sistema de firma digital.
Dado que los chips están físicamente integrados en las tarjetas de identificación, volver a emitir claves significa volver a emitir cada identificación. Panamá debe aprender de este error utilizando una clave separada que esté vinculada de manera única a un número de cedula, pero que en realidad no esté incrustada en la tarjeta. Tal sistema permitiría reprogramar y reaprovisionar tarjetas con una simple visita a la empresa de telecomunicación emisora o al Tribunal Electoral.
### Pagos del Canal
Los pagos del canal se procesan actualmente a través del sistema bancario, con tiempos de liquidación de varios días y tarifas significativas. Los pagos de Balboa Coin se liquidarán en segundos y no tendrán cargos. Asumiendo ingenuamente que las tarifas bancarias sean del 1%, se podría lograr un ahorro de $10 millones por cada $1,000 millones en pagos del canal.
### Aplicaciones de Usuario
Se necesitará desarrollar dos aplicaciones para que los pagos fluyan. La primera sería una aplicación de monedero con la que todos los usuarios podrían enviar y recibir Balboa Coins. La segunda sería una aplicación de administración de canal, para emitir facturas e informes en ejecución.
El libro de registro contable de Balboa Coin y los documentos gobernantes se almacenarán inmutablemente utilizando el sistema de archivos libre y de código abierto [guld filesystem] [7](https://guld.io/docs/guldFS-Specification.pdf "Ira Miller “Guld Filesystem Specification”, 2017"). Este no es el único árbol hash distribuido que podría usarse, ya que otros países están desarrollando fuera de Ethereum y otras plataformas. Sin embargo, estos no son compatibles con esquemas de firma de identidad digital como RSA, y no pueden asignar esquemas de tarifa personalizados debido a limitaciones de cambio de escala.
### Alternativa Manual
TODO: Describe un método donde los usuarios que no tengan teléfonos celulares o acceso general a redes digitales podrían acceder a sus cuentas. Podría ser a través de una ventana gubernamental o un agente como un banco.
## Finanzas
### Costos
Al utilizar tecnologías maduras y de código abierto, Balboa Coin podría ejecutarse a un costo muy bajo, del orden de $40 millones para configurar todo el país, o aproximadamente $10 por persona.
| Ítem | Estimación de costos | | Tarjetas SIM openPGP | $ 30 millones | | Desarrollo de software | $ 5 millones | | Incorporación del usuario | $ 5 millones |
### Tarjetas SIM OpenPGP
Estas tarjetas sim especiales convertirán cada teléfono panameño en su cedula digital y en la interfaz del Canal. Esto permitirá a todos los panameños con acceso a un teléfono celular y un número de cedula puedan acceder al sistema de Balboa Coin. Como hay más teléfonos celulares que personas en Panamá, esto debería cubrir a toda la población.
La estimación de $30 millones se basa en un costo de $7.5/sim. En Panamá, la tarjeta de $2-3 es estándar, pero tendríamos que agregar el soporte de OpenPGP y verificar formalmente tanto el hardware como el firmware.
### Desarrollo de Software
Se necesitaría una aplicación de monedero para las personas y una aplicación de administración del Canal por separado.
La aplicación de monedero podría parecerse a cualquier monedero de banca en línea o criptomoneda. Al usar estándares de código abierto, se podrían desarrollar múltiples monederos para llegar a diferentes usuarios. Por ejemplo, la aplicación bancaria [Nequi] [8](https://www.nequi.com.pa "Nequi banking app") y el monedero blockchain [jaxx] [9](https://jaxx.io "Jaxx digital currency wallet") podrían integrarse y enviarse Balboa Coins entre sí.
En cuanto a la administración, existen muchos usuarios empresariales de blockchains de los que se puede aprender. Dubái y Rusia recientemente han expresado sus planes de emitir dólares digitales (en realidad dirhams y rublos) en el blockchain de Ethereum.
El Banco Central de Barbados emitió un dólar digital en el blockchain de Bitcoin en 2015 con la ayuda de Bitt. Recientemente, Bitt publicó un plan para la [Cámara de Compensación Multilateral del Banco Central] [10](https://www.bitt.com/solutions/central-banks "Roland Haggins, Oliver Gale, Gabriel Abed, Simon Chantry “Central Bank Digital Currency Issuance”"). Al emitir un dólar digital que cumpla con los estándares de tecnología criptográfica, Panamá podría celebrar acuerdos de intercambio bilaterales y multilaterales con la liquidación de transacciones directa y en tiempo real. No se necesita un banco central.
Todos los usuarios de Balboa Coins podrían también tener acceso a pagos internacionales directos y al intercambio con contrapartes en Barbados, Dubái, Estonia y otros países con estándares de dólares digitales.

### Incorporación del Usuario
Se necesitará mucha educación, así como la logística para registrar las claves digitales de todos. Los usuarios podrían ser incorporados a través del Tribunal Electoral y sus telecomunicaciones. El costo de $5 millones necesita un mayor análisis con más datos de los expertos.
### Ingresos
#### Año 1
Durante el primer año, la Autoridad del Canal de Panamá continuará operando el canal como de costumbre. Al final del año fiscal, si se han obtenido ganancias, esas ganancias se depositarán en Balboa Coin Trust, y se emitirá 1 moneda XBC por cada $1 depositado. Estas nuevas monedas de XBC se distribuirían de manera uniforme a cada ciudadano panameño con cédula, pagándoles efectivamente un dividendo como propietarios del Canal.
Para 2017 los ingresos del canal fueron de [$1.909 billones] [11](aguaclara.consulting/s/1-Informe-Economico-Panama-kpg6.pdf "Aristides Hernandez, Eloy Fisher “ECONOMIC REPORT OF PANAMA: Global and Regional Environment”, Jan. 2018, pp. 9"), por lo que podríamos esperar que se emitan 1.909 billones de XBC al final del primer año. Dado que hay [3.753 millones de panameños] [12](https://www.cia.gov/library/publications/the-world-factbook/geos/pm.html "CIA World Factbook (July 2017 est.)") , cada uno recibiría 508.65 de XBC. Cada uno de estos XBC estaría respaldado por $1 que se mantendría en Balboa Coin Trust. Esto representa 1.2 meses con un salario mínimo de $416.
#### Año 2
Durante el segundo año, la Autoridad del Canal de Panamá agregaría XBC como una opción de pago adicional. Si una compañía naviera puede adquirir XBC en el mercado abierto, comprando a panameños, podrán hacer pagos preferidos más rápidos para el Canal.
Mientras tanto, el Balboa Coin Trust tendría $1.909 billones para invertir. Obviamente, este Trust debe manejarse de manera conservadora, invirtiendo en activos estables como oro y bonos. ¡Estrictamente no Cryptokitties!
Si se logra un rendimiento conservador del 3% anual, se obtendría una ganancia de $57.27 millones por los $1.909 billones. Esto excede los costos de configuración estimados para el programa, pagándolo por completo en el segundo año.
#### Año 3
Con el tiempo, el Balboa Coin Trust acumularía un superávit mayor, traspasando los pagos de intereses o los rendimientos de bonos del capital y agregando las ganancias.
#### Año 12
La deuda pública fue de $23.466 mil millones en 2017. Suponiendo ingenuamente que la deuda pública y las ganancias del canal se mantengan relativamente iguales, Balboa Coin Trust tendrá un dólar por cada dólar de deuda pública para el año 12.
### Presupuesto del Gobierno
Teóricamente, el impacto del presupuesto del gobierno podría ser neutral, si el 100% del Balboa Coin Trust se les prestara como bonos sin interés. En el escenario de rendimiento de bonos del 3% descrito anteriormente, ese 3% sería pagado por el gobierno al Balboa Coin Trust, otra acción neutral para el sector público en general.
### Balboa Coin Trust
Balboa Coin Trust operaría con un estricto mandato de $1: XBC. Se requerirá mantener todos sus registros contables en el árbol hash distribuido elegido y se realizará una auditoría completa una vez al año cuando se emita el nuevo dividendo.
## Impacto Social
### Ingreso Básico Universal
“Ingreso Básico Universal (UBI por sus siglas en inglés) se puede describir como una forma incondicional de pago por transferencia para la totalidad de la población, sin tomar en consideración los requisitos de trabajo. Es una idea que está generando un gran interés en los debates a través del espectro político como un posible método para lidiar con los pronósticos que advierten contra un futuro terrible de extrema desigualdad impulsado por factores tanto socioeconómicos como tecnológicos". [Ingreso Básico Universal: Un Análisis] [13](https://ssrn.com/abstract=3013634 "Chohan, Usman, Universal Basic Income: A Review (August 4, 2017).")
### Servicios Financieros para los No Bancarizados
Todos los panameños obtendrían acceso a los servicios financieros básicos utilizando la aplicación de monedero de Balboa Coin. En 2014, el Banco Mundial estimó que solo [el 44% de los adultos panameños tenían cuentas bancarias] [14](http://documents.worldbank.org/curated/en/187761468179367706/pdf/WPS7255.pdf "Asli Demirguc-Kunt, Leora Klapper, Dorothe Singer, Peter Van Oudheusden “The Global Findex Database”, 2014"), por lo que esto duplicaría con creces el acceso a los servicios financieros.
Además, los servicios financieros ofrecidos por Balboa Coin no tendrían ningún costo, en comparación con las tarifas bancarias de transferencia de dinero de hasta 10%, que afectan desproporcionadamente a los pobres.
## Glosario

* 	**Árbol hash distribuido:** estructura de datos inmutables que permite una contabilización perfecta de triple entrada, como un blockchain o blocktree.

* 	**Balboa Coin** - ficha respaldada por US $1, que puede canjearse por el paso del Canal de Panamá.

* 	**XBC:** código de moneda compatible con ISO para Balboa Coin.