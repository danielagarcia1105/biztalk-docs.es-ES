---
title: 'Paso 5: Realizar pruebas de patrón de carga de paso para determinar el rendimiento máximo sostenible | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8056ced6-1f04-4be2-878a-48a427a93dad
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f9794634b5a782ef6d9bce4e819e759fd47ba1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302644"
---
# <a name="step-5-perform-step-load-pattern-tests-to-determine-maximum-sustainable-throughput"></a>Paso 5: Realizar pruebas de patrón de carga de paso para determinar el rendimiento máximo sostenible
El método más sencillo para determinar el rendimiento sostenible máximo (MST) de una solución de BizTalk Server con pruebas de carga de Visual Studio consiste en realizar un modelo de carga de pasos y comparar el número total de documentos recibido por segundo para el total del documento procesada por segundo . Siempre que el promedio total de documentos procesados por segundo es mayor o igual que el promedio total de documentos recibido por segundo para la duración de la prueba, se considera la carga sostenible. Si el promedio total de documentos recibido por segundo es mayor que el promedio total de documentos procesados por segundo para la duración de la prueba, a continuación, la carga no se considera sostenible y esto se detectado por una aumento correspondiente en el valor de la Contador de tamaño de Counters\Spool cuadro: General de BizTalk. Con el tiempo, cuando una aplicación de BizTalk Server recibe los documentos más de los que puede procesar, los documentos sin procesar se acumularán en la base de datos de cuadro de mensajes, que se puede producir una condición de limitación y degradar significativamente el rendimiento de la Aplicación de BizTalk Server.  
  
## <a name="configure-the-load-test-with-a-step-load-pattern-appropriate-for-your-application"></a>Configurar la prueba de carga con un modelo de carga de pasos adecuado para la aplicación  
 Siga los pasos descritos en el tema [paso 3: crear una prueba de carga para realizar pruebas de unidad varios simultáneamente](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md) para crear una prueba de carga que utiliza un modelo de carga de pasos. Factores que afectan a la capacidad de la aplicación de BizTalk Server para procesar documentos de manera oportuna incluyen:  
  
-   **Número de equipos con BizTalk Server en el grupo de** -servidores de BizTalk adicionales proporcionan la capacidad de procesamiento adicional.  
  
-   **Tamaño de los mensajes que se va a procesar** -mensajes más grandes requieren recursos de procesamiento adicional.  
  
-   **Cantidad de asignación de documento realiza** -asignación requiere recursos de procesamiento adicionales.  
  
-   **Recibir o enviar canalizaciones requeridas por la aplicación**. -Canalizaciones complejas requieren recursos de procesamiento adicionales.  
  
-   **Adaptadores o aceleradores utilizados por la aplicación de BizTalk Server** : algunos adaptadores o aceleradores requieren más recursos de procesamiento que otros usuarios.  
  
-   **Cantidad de seguimiento de mensajes necesario** : seguimiento de mensajes es una cantidad de recursos.  
  
-   **Número de y la complejidad de orquestaciones que se ejecutan en la aplicación de BizTalk Server** : las orquestaciones pueden ser precisa muchos recursos.  
  
 Al configurar el paso de la prueba de modelo de carga, modifique los valores especificados para **iniciar cuenta de usuario** y **recuento máximo de usuarios** para asegurarse de que el número de mensajes que se especificó para recuento de usuarios de inicio puede ser fácilmente controlado por el servidor BizTalk Server la aplicación con el tiempo y del mismo modo, el número de mensajes especificados de recuento máximo de usuarios es superior al que la aplicación de BizTalk Server puede controlar con el tiempo. Vea [agregar una prueba de carga y configurar el escenario de prueba de carga, los conjuntos de contadores y los parámetros de ejecución](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_StepLoadTest) para obtener información acerca de cómo modificar la configuración del modelo de carga para la prueba de carga.  
  
## <a name="ensure-that-the-correct-test-settings-are-used-for-the-step-pattern-load-test"></a>Asegúrese de que la configuración correcta de la prueba se usa para la prueba de carga de patrón de paso  
 Configurar la prueba de carga para usar el **configuración de pruebas** que creó en [agregar un archivo de configuración a la solución para ejecutar pruebas y recopilar datos de forma remota](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_TestSettings).  
  
## <a name="configure-the-load-test-with-the-appropriate-performance-counters-and-run-the-step-pattern-load-test"></a>Configurar la prueba de carga con los contadores de rendimiento adecuado y ejecutar la prueba de carga de patrón de paso  
 Siga los pasos de [agregar un conjunto de contadores personalizados a indicadores de rendimiento de clave (KPI) de medida BizTalk Server](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters) para agregar los contadores de rendimiento de BizTalk Server es necesarios que se pueden usar para medir el rendimiento de BizTalk Server Aplicación y determinar en qué punto la aplicación BizTalk Server ya no es capaz de mantener la carga de mensajes creada por los agentes de prueba de carga. Esto se manifiesta por la acumulación de una acumulación de mensajes en la tabla de cola de impresión, tal como lo ve un valor mayor para el contador tamaño de Counters\Spool cuadro: General de BizTalk. Si el valor de este contador comienza a aumentar de forma significativa, a continuación, probablemente ha excedido el MST de su aplicación de BizTalk Server. Una vez haya determinado el número de mensajes en el que la aplicación BizTalk Server ya no es capaz de procesar muchos mensajes tal y como lo recibe, tome nota de los documentos recibidos/seg. Cuando esto ocurre. Es importante que anote este valor porque el tema [paso 6: realizar constante patrón de pruebas de carga para comprobar el rendimiento máximo sostenible](../technical-guides/step-6-complete-load-pattern-tests-to-verify-maximum-sustainable-throughput.md) se describe cómo ejecutar una prueba de carga de patrón constante con un valor de "Recuento de usuarios constante" que es ligeramente menor que el valor máximo de sostenible documentos recibidos/seg.. Esto sirve para comprobar que la aplicación de BizTalk Server es capaz de procesar este número de mensajes con el tiempo. Para ver los valores de conjuntos de contadores, inicie la prueba de carga haciendo clic en el nombre de la prueba (por ejemplo, BTS_Messaging_Step) y, a continuación, haga clic en el **Ejecutar prueba** opción de menú. Después de que se inicializan los contadores de rendimiento y comienza la prueba de carga, Visual Studio cambiará automáticamente la atención a la ventana de gráficos que le permite mostrar desde 1 a 4 gráficos al mismo tiempo. Si le interesa principalmente en ver solo los indicadores clave de rendimiento, como se define en [agregar un conjunto de contadores personalizados a indicadores de rendimiento de clave (KPI) de medida BizTalk Server](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters), haga clic en el **paneles** lista desplegable lista en el menú de prueba de carga y seleccione la opción para **un Panel**. A continuación, haga clic en la lista desplegable en la parte superior del gráfico y seleccione **indicadores clave de** para mostrar los valores de los indicadores clave de rendimiento en tiempo real.  
  
> [!NOTE]  
>  Dado que ciertos valores de contador de forma predeterminada se mostrará en el **indicadores clave** graph y porque probablemente deseará mostrar los valores de contador que agregó al conjunto de contadores personalizado, puede que desee iniciar eliminando manualmente cada uno los contadores que se muestran en la **indicadores clave** graph y, a continuación, agregar manualmente los contadores de los conjuntos de contadores personalizados. Por ejemplo, al menos, debería agregar al menos los contadores en la tabla siguiente para el gráfico para determinar el grado el entorno de BizTalk Server lleva a cabo la carga y donde se pueden producir cuellos de botella:  
  
|Categoría de contador|Contador|Instancia|Computer|  
|----------------------|-------------|--------------|--------------|  
|BizTalk:Cuadros de mensajes:Contadores generales|Tamaño de cola de impresión|*Base de datos de cuadro de mensaje de BizTalk Server*:*instancia de SQL Server que aloja la base de datos de cuadro de mensaje de BizTalk Server*|Cualquier servidor de BizTalk en el grupo con la consola de administración de BizTalk Server instalado.|  
|BizTalk:Mensajería|Documentos recibidos/seg.|RxHost (o nombre de host de recepción)|*Equipo de BizTalk Server #1 en el grupo de BizTalk Server*|  
|BizTalk:Mensajería|Documentos recibidos/seg.|RxHost (o nombre de host de recepción)|*Equipo de BizTalk Server 2 en el grupo de BizTalk Server*|  
|BizTalk:Mensajería|Documentos recibidos/seg.|RxHost (o nombre de host de recepción)|*Equipo de BizTalk Server #n en el grupo de BizTalk Server*|  
|BizTalk:Mensajería|Documentos procesados/seg.|TxHost (o nombre de host de envío)|*Equipo de BizTalk Server #1 en el grupo de BizTalk Server*|  
|BizTalk:Mensajería|Documentos procesados/seg.|TxHost (o nombre de host de envío)|*Equipo de BizTalk Server 2 en el grupo de BizTalk Server*|  
|BizTalk:Mensajería|Documentos procesados/seg.|TxHost (o nombre de host de envío)|*Equipo de BizTalk Server #n en el grupo de BizTalk Server*|  
|Procesador|% de tiempo de procesador|_Total|*Equipo de BizTalk Server #1 en el grupo de BizTalk Server*|  
|Procesador|% de tiempo de procesador|_Total|*Equipo de BizTalk Server 2 en el grupo de BizTalk Server*|  
|Procesador|% de tiempo de procesador|_Total|*Equipo de BizTalk Server #n en el grupo de BizTalk Server*|  
|Procesador|% de tiempo de procesador|_Total|*Instancia de SQL Server que hospeda las bases de datos de BizTalk Server*|