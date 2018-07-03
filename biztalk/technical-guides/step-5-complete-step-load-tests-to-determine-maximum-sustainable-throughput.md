---
title: 'Paso 5: Realizar pruebas de patrón de carga de pasos para determinar el rendimiento máximo sostenible | Microsoft Docs'
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
ms.openlocfilehash: 223d8e444bbfc05960f2266e0c23eb0f1a90d9ee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987573"
---
# <a name="step-5-perform-step-load-pattern-tests-to-determine-maximum-sustainable-throughput"></a>Paso 5: Realizar pruebas de patrón de carga de pasos para determinar el rendimiento máximo sostenible
Es el método más sencillo para determinar el rendimiento sostenible máximo (MST) de una solución de BizTalk Server con las pruebas de carga de Visual Studio realizar un modelo de carga de pasos y comparar el número total de documentos recibido por segundo para el total del documento procesada por segundo . Siempre y cuando el promedio total de documentos procesado por segundo es mayor o igual que el promedio total de documentos recibido por segundo para la duración de la prueba, se considera la carga sostenible. Si el promedio total de documentos recibido por segundo es mayor que el promedio total de documentos procesados por segundo para la duración de la prueba, entonces no se considera la carga sostenible y esto se demuestra un crecimiento correspondiente en el valor de la Contador de BizTalk: cuadro de General Counters\Spool tamaño. Con el tiempo, cuando una aplicación de BizTalk Server recibe más documentos que puede procesar, se acumularán los documentos sin procesar en la base de datos de cuadro de mensajes, lo que finalmente inducir una condición de limitación y degradar significativamente el rendimiento de la Aplicación de BizTalk Server.  
  
## <a name="configure-the-load-test-with-a-step-load-pattern-appropriate-for-your-application"></a>Configurar la prueba de carga con un modelo de carga de pasos adecuado para su aplicación  
 Siga los pasos descritos en el tema [paso 3: crear una prueba de carga para realizar pruebas de unidad varios simultáneamente](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md) para crear una prueba de carga que utiliza un modelo de carga de pasos. Los factores que afectan a la capacidad de la aplicación de BizTalk Server procesar documentos de manera oportuna incluyen:  
  
- **Número de equipos de BizTalk Server en el grupo** -servidores de BizTalk adicionales proporcionan la capacidad de procesamiento adicional.  
  
- **Tamaño de los mensajes que se están procesando** -mensajes más grandes requieren recursos de procesamiento adicional.  
  
- **Cantidad de asignación de documentos realiza** -asignación requiere recursos de procesamiento adicionales.  
  
- **Recibir o enviar canalizaciones requeridas por la aplicación**. -Canalizaciones complejas requieren recursos de procesamiento adicional.  
  
- **Los adaptadores o aceleradores utilizados por la aplicación de BizTalk Server** : algunos adaptadores o aceleradores requieren más recursos de procesamiento que otras.  
  
- **Cantidad de seguimiento de mensajes necesario** : seguimiento de mensajes es consumen muchos recursos.  
  
- **Número de y la complejidad de las orquestaciones que se ejecutan en la aplicación de BizTalk Server** – las orquestaciones pueden ser consume muchos recursos.  
  
  Al configurar el paso de la prueba de patrón de carga, modificar los valores especificados para **iniciar recuento de usuarios** y **recuento máximo de usuarios** para asegurarse de que el número de mensajes especificado para el recuento de usuarios de inicio puede ser fácilmente controlado por el servidor BizTalk Server la aplicación con el tiempo y del mismo modo, el número de mensajes especificado para el recuento máximo de usuarios es más que la aplicación de BizTalk Server puede controlar con el tiempo. Consulte [agregar una prueba de carga y configurar el escenario de prueba de carga, conjuntos de contadores y parámetros de ejecución](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_StepLoadTest) para obtener información acerca de cómo modificar la configuración de patrón de carga para la prueba de carga.  
  
## <a name="ensure-that-the-correct-test-settings-are-used-for-the-step-pattern-load-test"></a>Asegúrese de que la configuración correcta de la prueba se usan para la prueba de carga del patrón de paso  
 Configurar la prueba de carga para usar el **configuración de pruebas** que creó en [agregar un archivo de configuración a la solución para ejecutar pruebas y recopilar datos remotamente](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_TestSettings).  
  
## <a name="configure-the-load-test-with-the-appropriate-performance-counters-and-run-the-step-pattern-load-test"></a>Configurar la prueba de carga con los contadores de rendimiento adecuado y ejecutar la prueba de carga del patrón de paso  
 Siga los pasos de [agregar un conjunto de contadores personalizados a los indicadores de rendimiento de clave (KPI) de medida BizTalk Server](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters) para agregar los contadores de rendimiento de BizTalk Server es necesarios que se pueden usar para medir el rendimiento de BizTalk Server Aplicación y determinar en qué punto la aplicación de BizTalk Server ya no es capaz de mantener la carga de mensaje creada por los agentes de prueba de carga. Esto se hace evidente por la acumulación de un trabajo pendiente de mensajes en la tabla de cola de impresión tal como lo ve un valor mayor para el contador tamaño de BizTalk: cuadro de General Counters\Spool. Si el valor de este contador comienza a aumentar de forma significativa, a continuación, probablemente ha superado el MST de su aplicación de BizTalk Server. Una vez haya determinado el número de mensajes en el que la aplicación de BizTalk Server ya no es capaz de procesar muchos mensajes que recibe, tome nota de los documentos recibidos/seg. Cuando esto ocurre. Es importante tomar nota de este valor porque el tema [paso 6: realizar constante patrón las pruebas de carga para comprobar el rendimiento máximo sostenible](../technical-guides/step-6-complete-load-pattern-tests-to-verify-maximum-sustainable-throughput.md) se describe cómo ejecutar una prueba de carga de patrón de constante con un valor de "Recuento de usuarios constante" que es un poco más pequeño que el valor máximo de sostenible documentos recibidos por segundo. Esto sirve para comprobar que la aplicación de BizTalk Server es capaz de procesar este número de mensajes con el tiempo. Para ver los valores de conjuntos de contadores, iniciar la prueba de carga haciendo clic con el nombre de la prueba (por ejemplo, BTS_Messaging_Step) y, a continuación, haga clic en el **Ejecutar prueba** opción de menú. Después de que se inicializan los contadores de rendimiento y comienza la prueba de carga, Visual Studio cambiará automáticamente el foco a la ventana de gráficos que le permite mostrar simultáneamente desde 1 a 4 gráficos. Si le interesa principalmente en ver solo los indicadores clave de rendimiento, como se define en [agregar un conjunto de contadores personalizados a los indicadores de rendimiento de clave (KPI) de medida BizTalk Server](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters), haga clic en el **paneles** lista desplegable lista en el menú de prueba de carga y seleccione la opción de **un Panel**. A continuación, haga clic en la lista desplegable en la parte superior del gráfico y seleccione **indicadores clave de** para mostrar valores para los indicadores clave de rendimiento en tiempo real.  
  
> [!NOTE]  
>  Dado que ciertos valores de contador de forma predeterminada se mostrará en el **indicadores clave de** de graph y dado que probablemente desea mostrar los valores de contador que agregó al conjunto de contadores personalizado, es posible que desea iniciar eliminando manualmente cada uno los contadores que se muestra en el **indicadores clave de** del gráfico y, a continuación, agregar manualmente los contadores de los conjuntos de contadores personalizados. Por ejemplo, al menos, podría desea agregar al menos los contadores en la tabla siguiente en el gráfico para determinar el grado en que el entorno de BizTalk Server asume la carga y donde se pueden producir cuellos de botella en:  
  
|Categoría de contador|Contador|Instancia|Computer|  
|----------------------|-------------|--------------|--------------|  
|BizTalk:Cuadros de mensajes:Contadores generales|Tamaño de cola de impresión|*Base de datos de cuadro de mensaje de BizTalk Server*:*instancia de SQL Server que aloja la base de datos de cuadro de mensaje de BizTalk Server*|Cualquier servidor de BizTalk en el grupo con la consola de administración de BizTalk Server instalado.|  
|BizTalk:Mensajería|Documentos recibidos/seg.|RxHost (o nombre de host de recepción)|*Equipo de BizTalk Server Nº 1 en el grupo de BizTalk Server*|  
|BizTalk:Mensajería|Documentos recibidos/seg.|RxHost (o nombre de host de recepción)|*Equipo de BizTalk Server #2 en el grupo de BizTalk Server*|  
|BizTalk:Mensajería|Documentos recibidos/seg.|RxHost (o nombre de host de recepción)|*Equipo de BizTalk Server #n en el grupo de BizTalk Server*|  
|BizTalk:Mensajería|Documentos procesados/seg.|TxHost (o nombre de host de envío)|*Equipo de BizTalk Server Nº 1 en el grupo de BizTalk Server*|  
|BizTalk:Mensajería|Documentos procesados/seg.|TxHost (o nombre de host de envío)|*Equipo de BizTalk Server #2 en el grupo de BizTalk Server*|  
|BizTalk:Mensajería|Documentos procesados/seg.|TxHost (o nombre de host de envío)|*Equipo de BizTalk Server #n en el grupo de BizTalk Server*|  
|Procesador|% de tiempo de procesador|_Total|*Equipo de BizTalk Server Nº 1 en el grupo de BizTalk Server*|  
|Procesador|% de tiempo de procesador|_Total|*Equipo de BizTalk Server #2 en el grupo de BizTalk Server*|  
|Procesador|% de tiempo de procesador|_Total|*Equipo de BizTalk Server #n en el grupo de BizTalk Server*|  
|Procesador|% de tiempo de procesador|_Total|*Instancia de SQL Server que aloja las bases de datos de BizTalk Server*|