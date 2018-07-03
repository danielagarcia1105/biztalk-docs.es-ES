---
title: Definición de datos en BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- monitoring business activities [BAM], BAM Activity Wizard
- monitoring business activities [BAM], time intervals
- aggregations [BAM], measurements
- monitoring business activities [BAM], views
- monitoring business activities [BAM], aggregations
- Excel add-in [BAM], collecting data
- aggregations [BAM], scheduling
- monitoring business activities [BAM], milestone groups
- aggregations [BAM], real-time data
ms.assetid: 501a1c08-3979-4a99-94d9-0d1b5ec4266b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2caba09d12e6a7736ae452ffe05e7604ca5dea02
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986013"
---
# <a name="defining-data-in-bam"></a>Definir datos en BAM
El complemento de BAM para Excel sirve para definir los datos que BAM debe recopilar y para definir la forma en que se compartirán. Las actividades de BAM sirven para definir datos; las vistas de BAM, para definir los datos que pueden ver otros usuarios.  
  
## <a name="activities"></a>Actividades  
 Una actividad de BAM se crea para definir la información sobre un proceso empresarial que se desea supervisar mediante BAM. Una actividad de BAM representa un proceso empresarial específico de la empresa, tal como la administración de pedidos de compra o el envío de un producto. Un proceso empresarial tiene un conjunto definido de hitos y datos económicos. Por ejemplo, un proceso de pedido de compra puede disponer de hitos como Aprobado, Denegado y Entregado, junto con datos económicos como Nombre de cliente y Producto.  
  
 El propósito de una actividad de BAM es mostrar el historial (hitos) y los datos de un proceso a los trabajadores de la información. Las actividades de BAM son abstracciones de alto nivel independientes de la implementación real de BizTalk Server. Para obtener información general conceptual sobre BAM, vea el tema "Supervisión de la actividad económica" de la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 El Asistente para actividad de BAM permite definir actividades de BAM que contienen al menos un elemento de actividad. El usuario agrupa elementos de actividad relacionados en una actividad, y usa los elementos de actividad para describir el tipo de datos de un proceso empresarial que desea hacer disponible.  
  
 En la tabla siguiente se describen los tipos de elementos de actividad que proporciona BAM.  
  
|Tipo de elemento|Descripción|  
|---------------|-----------------|  
|Hito económico|Un valor de fecha y hora. Por ejemplo, la fecha de aprobación de un pedido de compra.|  
|Datos económicos: Text|Cadena que contiene cualquier carácter alfanumérico. Por ejemplo, enviar: código de ciudad, estado o provincia y código Postal.|  
|Datos económicos: entero|Valor numérico entero. Por ejemplo el número total de compras.|  
|Datos económicos: Float|Valor decimal. Por ejemplo el importe total del pedido de compra.|  
  
 Por ejemplo, en una actividad de pedido de compra podría crear los elementos de actividad de la tabla siguiente.  
  
|Elemento de actividad|Tipo de elemento|  
|-------------------|---------------|  
|Product|Datos económicos: Text|  
|City|Datos económicos: Text|  
|State|Datos económicos: Text|  
|Amount|Datos económicos: Float|  
|Cantidad|Datos económicos: entero|  
|Aprobada|Hito económico|  
|Entregado|Hito económico|  
|Denegado|Hito económico|  
|Recibida|Hito económico|  
  
 Tenga en cuenta que Importe es de tipo Float, ya que puede ser un valor decimal. Cantidad es de tipo Integer porque siempre será un número entero en este ejemplo. Aprobado, Entregado, Denegado y Recibido son hitos del proceso del pedido de compra.  
  
## <a name="views"></a>Vistas  
 Puede crear vistas para mostrar datos de una actividad a los usuarios. Al crear una vista basada en la actividad de pedido de compra, debe definir los datos detrás de los elementos de la actividad. Los datos de una vista de BAM se definen como dimensiones, medidas, duraciones, grupos de hitos y dimensiones de progreso.  
  
 Una vista contiene uno o más elementos de vista. Puede crear los siguientes tipos de elementos de vista:  
  
-   Duraciones  
  
-   Grupos de hitos  
  
-   Agregaciones  
  
### <a name="durations"></a>Duraciones  
 Las duraciones son intervalos de tiempo y se describen mediante los hitos que definen el inicio y el final de los intervalos de tiempo. En la tabla siguiente se muestran las duraciones que puede definir a partir de los hitos mostrados en la tabla anterior.  
  
|Duration|Hito de inicio|Hito de fin|  
|--------------|---------------------|-------------------|  
|1|Recibida|Aprobada|  
|2|Recibida|Entregado|  
|3|Recibida|Denegado|  
|4|Aprobada|Entregado|  
  
 En esta tabla, puede ver que la primera duración (Duración 1) es el intervalo de tiempo que comienza cuando el servidor BizTalk Server recibe un pedido de compra y termina cuando este último se aprueba.  
  
### <a name="milestone-groups"></a>Grupos de hitos  
 Los grupos de hitos se crean para tratar un conjunto de hitos (por ejemplo los hitos inicial y final de un proceso) como una sola entidad, lo que crea un solo hito que representa toda la longitud del proceso.  
  
### <a name="aggregations"></a>Agregaciones  
 Las agregaciones sirven para mejorar el tiempo de respuesta al actualizar datos de la base de datos. Excel define las agregaciones como resúmenes de datos precalculados que mejoran el tiempo de respuesta de consultas al tener preparadas las respuestas antes de que se planteen las preguntas. Por ejemplo, cuando una tabla de hechos de almacén de datos contiene cientos de miles de filas, una consulta que solicita las programaciones de envío de dos productos en concreto puede tardar en responder si la tabla de hechos se tiene que analizar para calcular la respuesta. Sin embargo, la respuesta puede ser casi inmediata si los datos de resumen para responder a esta consulta se han calculado previamente.  
  
 En la siguiente ilustración se muestra un ejemplo de los datos de agregación precalculados.  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
  
 En la ilustración se proporciona un resumen de los números de cada producto, enviados a las ubicaciones determinadas durante un período de tiempo de dos meses. Excel normalmente define estos datos como medida. Excel define como dimensión los datos que se usan para el filtrado y la categorización.  
  
 Puede definir dos tipos de agregaciones en el libro de trabajo de BAM:  
  
-   Agregaciones en tiempo real  
  
-   Agregaciones programadas  
  
### <a name="real-time-aggregations"></a>Agregaciones en tiempo real  
 Las agregaciones en tiempo real (ATR) permiten ver el estado actual del proceso empresarial e identificar fácilmente sus cuellos de botella.  
  
 Los datos de BAM se muestran en una tabla dinámica, que se puede definir como una ATR o como una agregación programada. Una ATR ofrece vista actualizada al minuto de los datos; por ejemplo, indica la posición de un pedido de compra específico en el proceso de envío. Puede actualizar la pantalla para actualizar la vista de los datos a lo largo del día.  
  
 En algunos casos, fragmentos específicos de agregaciones multidimensionales están tan sujetos a limitaciones variables en el tiempo que sería conveniente tenerlas disponibles en tiempo real. Por ejemplo, una empresa vende productos perecederos y el usuario desea tener disponible en tiempo real la agregación de la cantidad de productos en diferentes fases de entrega. Al mismo tiempo, también desea tener otras agregaciones, tal como la edad de los clientes, pero solo a finales de mes para el análisis de inteligencia empresarial.  
  
> [!IMPORTANT]
>  No defina varias ATR que usan la misma actividad de BAM . Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.  
  
 Para obtener información acerca de la exploración de datos multidimensionales, vea el tema sobre tablas dinámicas de la Ayuda de Excel.  
  
### <a name="scheduled-aggregations"></a>Agregaciones programadas  
 De forma predeterminada, todas las agregaciones de BAM son agregaciones programadas. Una agregación programada representa una instantánea de la empresa a una hora determinada, por ejemplo un resumen de los envíos de la mañana. Pregunte al administrador de base de datos cuándo se procesan las agregaciones y podrá consultar los datos históricos.  
  
### <a name="dimensions-and-measures"></a>Dimensiones y medidas  
 Las dimensiones y medidas sirven para crear agregaciones de datos:  
  
- Las dimensiones describen un hecho.  
  
- Las medidas son valores de hechos.  
  
  Por ejemplo, un hecho podría ser "3 automóviles rojos" en inventario. La descripción del producto: "car" y "rojo" son dimensiones. El valor del hecho "3" es una medida. Si el precio de cada automóvil se incluye en el hecho, dicho precio es una dimensión pero el precio medio de los automóviles en inventario es una medida. En Libros en pantalla de Microsoft SQL Server una medida se describe como "los valores centrales que se agregan y analizan". Es decir, si un elemento se puede contar, si se puede calcular su promedio o se le puede aplicar cualquier otra operación matemática para obtenerlo, se trata de una medida.  
  
  Puede crear los siguientes tipos de dimensiones:  
  
- Dimensión de progreso  
  
- Dimensión de datos  
  
- Dimensión de tiempo  
  
- Dimensión de rango numérico  
  
## <a name="progress-dimensions"></a>Dimensiones de progreso  
 BAM presenta un nuevo tipo de dimensión: la dimensión de progreso. Puede crear dimensiones de progreso para crear agregaciones relacionadas con el progreso de actividades aún en curso.  
  
 Por ejemplo, considere un proceso empresarial de compra en el que recibe 1.000 pedidos de compra. Puede usar la dimensión de progreso en filas para crear la tabla siguiente.  
  
|OrderProgress_Level1|Count|  
|---------------------------|-----------|  
|Recibida|1000|  
  
 A continuación puede abrir el proceso Recibido para ver más detalles sobre el progreso de las actividades, por ejemplo:  
  
|||Count|  
|------|------|-----------|  
|Recibida|Evaluando|300|  
||Aprobada|500|  
||Denegado|200|  
  
 Esto significa que de los 1.000 pedidos que recibió, 500 se aprobaron, 200 se denegaron y 300 se están evaluando en este momento.  
  
 Recibido, Aprobado y Denegado representan hitos. Los números correspondientes de la columna Número muestran cuántos pedidos han pasado por estos hitos. Evaluando es una fase por la que pasan los pedidos entre los hitos Recibido, Aprobado o Denegado.  
  
 Puede usar las dimensiones de progreso en combinación con cualquier otra dimensión. Por ejemplo, si usa la dimensión de progreso Progreso de pedido en las filas y la dimensión de datos Producto en las columnas, obtendrá los resultados siguientes:  
  
|||Raquetas de tenis|Balones de fútbol|  
|------|------|---------------------|------------------|  
|Recibida|Evaluando|250|50|  
||Aprobada|200|300|  
||Denegado|150|50|  
  
 Las dimensiones de progreso ofrecen información especialmente valiosa para gráficos basados en agregaciones en tiempo real (ATR). Las ATR permiten ver el estado actual del proceso empresarial e identificar fácilmente cuellos de botella en él.  
  
 Orden de los hitos de una compra de la dimensión de progreso puede ser secuencial: el primer paso se completa antes de inicia el paso siguiente. Otra posibilidad es completar los hitos conjuntamente. Los pasos secuenciales son pasos secundarios y los pasos conjuntos son pasos hermanos. En el proceso del pedido, la comprobación comienza en cuanto se recibe éste. Es un paso transitorio que tiene lugar al mismo tiempo que el hito Recibido y, por tanto, es un elemento hermano. Un pedido de compra solo se aprueba tras ser recibido; Aprobado es elemento secundario con respecto a Recibido.  
  
## <a name="data-dimension"></a>Dimensión de datos  
 Una dimensión de datos se define para usar el valor de ciertos elementos de texto de la actividad de BAM en filas o columnas. Por ejemplo, una dimensión de datos denominada Product puede usarse para crear la tabla siguiente:  
  
|Product|Count|  
|-------------|-----------|  
|Raquetas de tenis|100|  
|Balones de fútbol|200|  
  
 Además, puede definir más de una dimensión de datos en el Asistente para vistas de BAM. Por ejemplo, puede definir una dimensión de datos llamada Ubicación con niveles de Estado y Ciudad para crear la tabla siguiente:  
  
|Product|Los Angeles|San Francisco|Seattle|  
|-------------|-----------------|-------------------|-------------|  
|Raquetas de tenis|50|20|30|  
|Balones de fútbol|130|50|20|  
  
 En esta tabla se usó la dimensión Producto para las filas y la dimensión Ubicación para las columnas.  
  
## <a name="time-dimension"></a>Dimensión de tiempo  
 Puede crear una dimensión de tiempo para crear agregaciones con respecto al tiempo. Por ejemplo, una dimensión de tiempo se puede usar para crear la tabla siguiente:  
  
|Year|Month|Count|  
|----------|-----------|-----------|  
|2003|January|120|  
||February|230|  
||March|350|  
||April|280|  
  
 Puede combinar la dimensión de tiempo con cualquier otra dimensión. Por ejemplo, puede usar la dimensión de tiempo en filas y la dimensión de datos en columnas para crear la tabla siguiente:  
  
|Month|Raquetas de tenis|Balones de fútbol|  
|-----------|---------------------|------------------|  
|January|50|70|  
|February|120|110|  
|March|300|50|  
|April|220|60|  
  
## <a name="numeric-range-dimension"></a>Dimensión de rango numérico  
 Las dimensiones de rango numérico sirven para crear agregaciones que clasifican rangos de números mediante nombres descriptivos. Por ejemplo, un analista de negocios puede definir una dimensión de rango numérico llamada Tamaño del pedido de compra con los siguientes rangos:  
  
 Pequeño: para pedidos de compra de entre 0 y 100 USD  
  
 Mediano: para pedidos de compra de entre 100 y 1.000 USD  
  
 Grande: para pedidos de más de 1.000 USD  
  
> [!NOTE]
>  Si el importe de un pedido de compra no se encuentra en los rangos definidos (por ejemplo, si es menor que 0), BAM creará automáticamente una fila "Fuera de rango" para dar cabida a los datos de ese pedido.  
  
|Tamaño del pedido de compra|Count|  
|-------------|-----------|  
|Pequeño|500|  
|Media|350|  
|Grande|225|  
  
> [!NOTE]
>  No puede crear dos dimensiones de rango numérico que hagan referencia al mismo alias de datos.