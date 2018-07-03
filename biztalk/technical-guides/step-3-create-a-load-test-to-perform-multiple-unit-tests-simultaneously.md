---
title: 'Paso 3: Crear una prueba de carga para llevar a cabo al mismo tiempo varias pruebas unitarias | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5dd7e31-7188-4edf-9513-ea2725950b47
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d946c48c1bcaca420347771e73089e5535ab1229
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002709"
---
# <a name="step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously"></a>Paso 3: Crear una prueba de carga para llevar a cabo al mismo tiempo varias pruebas unitarias
Las pruebas de carga ejecutan varias instancias de uno o más pruebas unitarias para que se pueden medir el rendimiento y la capacidad de administrar la carga de la aplicación. Los componentes principales de una prueba de carga de Visual Studio 2010 incluyen:  
  
- **Escenarios** : la sección de una prueba de carga, donde configura el modelo de prueba de carga, el modelo de combinación de pruebas, combinación de pruebas, combinación de redes y combinación de exploradores Web. Escenarios de dar cabida a la complejidad de la simulación de perfiles de carga de trabajo complejas de mundo real. Para obtener una lista completa de todos los cargar propiedades del escenario de prueba vea [propiedades de escenario de prueba de carga](http://go.microsoft.com/fwlink/?LinkId=208327) (http://go.microsoft.com/fwlink/?LinkId=208327).  
  
- **Conjuntos de contadores** : la sección de una prueba de carga donde crear agrupaciones determinadas o "Conjuntos" de los contadores de rendimiento que se recopilen mientras se ejecuta la prueba de carga. Varios conjuntos de contadores predefinidos se proporcionan de forma predeterminada y se pueden agregar conjuntos de contadores personalizados. Por ejemplo, para evaluar la red puede crear un contador personalizado de rendimiento establecido, agregue los contadores de rendimiento de red pertinentes y guardarlo en la lista de conjuntos de contadores disponibles. Para obtener más información sobre cómo crear y guardar los conjuntos de contadores para pruebas de carga, consulte [especificar conjuntos de contadores para equipos en una prueba de carga](http://go.microsoft.com/fwlink/?LinkId=208328) (http://go.microsoft.com/fwlink/?LinkId=208328).  
  
- **Parámetros de ejecución** : parámetros de ejecución definen varios aspectos de una prueba de carga, como la duración de la prueba, los conjuntos de contadores que están asociados con diversos equipos durante la prueba de carga, diversas opciones de validación de prueba y las opciones de almacenamiento de resultados de pruebas. Puede crear y almacenar varios parámetros de ejecución para cada prueba de carga y, a continuación, seleccione una configuración determinada para utilizarla al ejecutar la prueba. Al crear la prueba de carga con el nuevo Asistente de prueba de carga, se agrega un parámetro de ejecución inicial a la prueba de carga. Para obtener una lista completa de todas las pruebas de carga las propiedades de configuración de ejecución, consulte [cargar Probar propiedades](http://go.microsoft.com/fwlink/?LinkId=208329) (http://go.microsoft.com/fwlink/?LinkId=208329).  
  
  Las pruebas de carga se crean mediante el nuevo Asistente de prueba de carga, puede editar con el Editor de prueba de carga y puede analizar en el analizador de prueba de carga. Todas estas herramientas se incluyen en Microsoft Visual Studio Ultimate edition. Para obtener más información sobre cómo crear y editar pruebas de carga en Visual Studio 2010 Ultimate edition, consulte [crear y editar pruebas de carga](http://go.microsoft.com/fwlink/?LinkId=208308) (http://go.microsoft.com/fwlink/?LinkId=208308).  
  
  Siga los pasos descritos en las secciones siguientes para agregar una carga de prueba para el proyecto de prueba descrito en [paso 1: crear una prueba unitaria para enviar documentos a BizTalk Server](../technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md). Estos pasos también describen cómo configurar el **escenarios**, **conjuntos de contadores**, y **parámetros de ejecución** para una prueba de carga.  
  
##  <a name="BKMK_StepLoadTest"></a> Agregar una prueba de carga y configurar el escenario de prueba de carga, conjuntos de contadores y parámetros de ejecución  
 Este tema describe cómo usar el **cargar el Asistente para prueba nueva** para agregar una carga de prueba a un proyecto de prueba y cómo configurar la carga de prueba para satisfacer necesidades específicas.  
  
### <a name="use-the-new-load-test-wizard-to-add-a-load-test-to-the-test-project"></a>Use el Asistente para nueva prueba de carga para agregar una prueba de carga al proyecto de prueba  
 Siga estos pasos para agregar una prueba de carga a un proyecto de prueba mediante el Asistente de prueba de carga de nuevo.  
  
1.  Abra el **prueba de carga** solución en Visual Studio 2010 si no está ya abierto.  
  
2.  Agregar una carpeta al proyecto BTSLoad; Esta carpeta contendrá las pruebas de carga que se crean como parte de este proyecto. En el Explorador de soluciones, haga clic en el proyecto BTSLoad, seleccione **agregar**y haga clic en **nueva carpeta**. Un icono de carpeta con el texto resaltado **NewFolder1** aparecerán bajo el proyecto BTSLoad, tipo **LoadTests** para cambiar el texto resaltado y presione la tecla ENTRAR para completar la creación de la carpeta C:\ Projects\LoadTest\BTSLoad\LoadTests.  
  
3.  En el Explorador de soluciones, haga doble clic en el **BTSLoad** , seleccione **agregar**y, a continuación, haga clic en **prueba de carga** para iniciar el **Asistente para prueba de carga nueva**.  
  
4.  Haga clic en **Siguiente**.  
  
5.  En el **editar la configuración para un escenario de prueba de carga** página **escriba un nombre para el escenario de prueba de carga:** tipo **BTS_Messaging_Step**. En **perfil de tiempo de reflexión** seleccione **no usar tiempos de reflexión** y, a continuación, haga clic en **siguiente**.  
  
6.  En el **Editar configuración del patrón de carga para una carga de escenario de prueba** página, seleccione **carga por pasos**, escriba los siguientes valores y, a continuación, haga clic en **siguiente**.  
  
    -   **Iniciar recuento de usuarios:** 30 usuarios  
  
    -   **Duración del paso:** 60 segundos  
  
    -   **Recuento de usuarios:** 10 usuarios  
  
    -   **Número máximo de usuarios** 80 usuarios  
  
    > [!NOTE]  
    >  Al aplicar la configuración de un paso del modelo de carga se debe calcular la cantidad de tiempo necesario para que todos los incrementos de paso completar. Por ejemplo, mediante la configuración del patrón de carga especificada anteriormente la prueba de carga necesita 5 minutos en completar todos los 60 segundos irá incrementos cuando refuerza de 30 en 80 usuarios. En la última página del nuevo asistente aparecerá con opciones para especificar la longitud de la prueba de carga, uno de los cuales será **duración de prueba de carga**. Si ya ha calculado el tiempo necesario para todos los incrementos para completar una tarea sencilla para escribir el valor (5 minutos en este caso) es el paso de **duración de la prueba de carga**.  
  
7.  En el **seleccionar un modelo de combinación de pruebas para la prueba de carga** página, seleccione **en función del número de usuarios virtuales** y, a continuación, haga clic en **siguiente**.  
  
8.  En el **agregar pruebas para el escenario de prueba de carga y editar la combinación de pruebas** página haga clic en el **agregar** botón.  
  
9. En **pruebas disponibles** haga doble clic en **BTSMessaging** y **BTSMessaging2** para agregar estas pruebas unitarias a la lista de **pruebas seleccionadas**. Haga clic en **Aceptar** y, a continuación, haga clic en **siguiente**.  
  
10. En el **agregar tipos de red a un escenario de prueba de carga y editar la combinación de redes** de comprobación de páginas que **tipo de red** está establecido en **LAN** con un **distribución** de **100%** y, a continuación, haga clic en **siguiente**.  
  
11. En el **especificar equipos para supervisar con conjuntos de contadores durante la ejecución de prueba de carga** página haga clic en **siguiente**.  
  
    > [!NOTE]  
    >  No agregue equipos a la prueba de carga en este momento. El nuevo asistente, solo podrá asociar los equipos con conjuntos de contadores predefinidos, y esta prueba de carga requiere el uso de ambos predefinidos y *personalizado* conjuntos de contadores. Tras finalizar el asistente y se guarda la prueba de carga puede editar la prueba de carga para agregar conjuntos de contadores personalizados y configurar la prueba de carga para supervisar equipos que usan ambos predefinidos *y* conjuntos de contadores personalizados.  
  
     En el **revisar y editar los parámetros para una prueba de carga de ejecución** página escriba los valores siguientes:  
  
    1.  Seleccione **duración de la prueba de carga**.  
  
    2.  **Duración de la preparación (hh mm ss)** 30 segundos  
  
    3.  **Duración (hh mm ss) de la serie** 5 minutos  
  
        > [!NOTE]  
        >  El tiempo asignado para **duración de la ejecución** debe ser igual a la cantidad de tiempo necesario para todos los paso incrementos para completar como se describe en el paso 5 anterior, o 5 minutos en este ejemplo.  
  
    4.  **Frecuencia de muestreo** 5 segundos  
  
    5.  **Descripción** (opcional), escriba una descripción para la prueba de carga aquí.  
  
    6.  **Guardar registro en el caso de error de prueba** True  
  
    7.  **Nivel de validación** bajo-invocar reglas de validación marcadas como bajos  
  
12. Haga clic en **finalizar** para cerrar el Asistente para nueva prueba de carga.  
  
13. Haga clic en el **archivo** menú y seleccione **guardar \<nombre de la prueba de carga\>.loadtest como**.  
  
    > [!NOTE]  
    >  En este ejemplo, <Load Test Name> será el nombre asignado al archivo de prueba de carga mediante Visual Studio 2010, normalmente loadtestx.loadtest, a menos que el nombre del archivo ya se ha cambiado manualmente.  
  
14. Guarde el archivo en el directorio C:\Projects\LoadTest\BTSLoad\LoadTests que creó anteriormente. Puede ser útil guardar el archivo con el nombre usado para el escenario; en este ejemplo el nombre del escenario es BTS_Messaging_Step por lo que el archivo de prueba de carga se guardaría como C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Step.loadtest.  
  
###  <a name="BKMK_BTSCounters"></a> Agregar un contador personalizado que establezca para medir indicadores clave de rendimiento de servidor BizTalk Server (KPI)  
 Siga estos pasos para agregar un contador establecido con contadores de rendimiento que miden el KPI de BizTalk Server necesarios para determinar la máxima sostenible rendimiento (MST) de la aplicación de BizTalk Server:  
  
1. En el doble clic del explorador de soluciones la prueba de carga que creó en la sección anterior para ver la prueba de carga en el editor de prueba de carga.  
  
2. En el editor de prueba de carga, haga clic para expandir **conjuntos de contadores**. Tenga en cuenta que no hay ningún conjunto de contadores predefinidos para BizTalk Server, por lo tanto, Establece el conjunto de contadores de "BizTalk Server" debe agregarse a la lista de contadores personalizado.  
  
3. Haga clic en **conjuntos de contadores** y seleccione **Agregar conjunto de contadores personalizados**. De forma predeterminada, esta acción creará un conjunto con el nombre de contadores personalizados **Custom1**.  
  
4. Haga clic en el **Custom1** contador establecido y seleccione **propiedades** para establecer el foco la **propiedades** cuadro de diálogo para el conjunto de contadores Custom1.  
  
5. Haga doble clic en el nombre **Custom1** en el **propiedades** cuadro de diálogo, escriba **BizTalk** y, a continuación, presione la tecla ENTRAR para cambiar el nombre del contador personalizado establecido en **BizTalk** .  
  
6. En el Editor de prueba de carga, haga clic en el **BizTalk** contador establecido y seleccione **agregar contadores**.  
  
7. En **equipo**, escriba el nombre de uno de los equipos de BizTalk Server en el grupo de BizTalk Server para mostrar las categorías de monitor de rendimiento que incluyen los contadores de rendimiento de BizTalk Server.  
  
   > [!IMPORTANT]
   >  Para asegurarse de que se enumeran todas las categorías de rendimiento de BizTalk Server y los contadores de rendimiento, es posible que deba escribir en el nombre de dominio completo (o dirección IP) de un servidor BizTalk Server en el grupo y también es posible que deba iniciar las instancias de los siguientes hosts en el Equipo de BizTalk Server.  
   > 
   > - Instancias de hosts de BizTalk que están enlazados a las orquestaciones que se ejecutarán durante la prueba de carga.  
   >   -   Instancias de hosts de BizTalk configurados como enviar o recibir controladores para los adaptadores que se ejecutarán durante la prueba de carga.  
  
8. BizTalk Server proporciona bastante un amplio conjunto de contadores de rendimiento. Para determinar el rendimiento sostenible máximo (MST) de un servidor BizTalk Server de contadores de aplicación sólo tiene que agregar el rendimiento de BizTalk Server siguiente a la **BizTalk** conjunto de contadores personalizados:  
  
   |Categoría de rendimiento|Contador de rendimiento|  
   |--------------------------|-------------------------|  
   |Procesador|% De tiempo de procesador para la instancia _Total del contador.|  
   |BizTalk cuadro: Contadores generales|Tamaño de cola de impresión el  *\<nombre de la base de datos de BizTalk MessageBox\>*:*\<nombre de instancia de SQL Server\>*  instancia del contador. **Nota:***\<nombre de la base de datos de BizTalk MessageBox\>*  y *\<nombre de instancia de SQL Server\>* son sólo marcadores de posición para el nombres reales de la base de datos de BizTalk MessageBox y la instancia de SQL Server que aloja la base de datos de BizTalk MessageBox.   Estos marcadores de posición se deben reemplazar con los nombres reales de la base de datos de BizTalk MessageBox y la instancia asociada de SQL Server.|  
   |BizTalk:Mensajería|Documentos recibidos/seg. de la instancia de contador de host de recepción.<br /><br /> Documentos procesados/seg. de la instancia de contador de host de transmisión.|  
   |BizTalk:Agente de mensaje|Tasa entrante de entrega de mensajes para el documento de host de recepción.|  
   |BizTalk:Agente de mensaje|Tasa saliente de publicación del mensaje para el host de transmisión del documento.|  
   |Orquestaciones XLANG/s|Orquestaciones completadas/s para el host de procesamiento de orquestación.|  
  
### <a name="modify-run-settings-to-map-counter-sets-to-appropriate-computers"></a>Modificar la configuración de ejecución para asignar conjuntos de contadores a los equipos adecuados  
 Siga estos pasos para asignar los conjuntos de contadores adecuados con los equipos apropiados para la prueba de carga:  
  
1.  En **Editor de prueba de carga**, haga clic en **parámetros de ejecución** y seleccione **administrar conjuntos de contadores**.  
  
2.  Haga clic en **Add Computer** para agregar un nuevo equipo a la lista. Un icono con el texto resaltado **nuevo equipo** aparecen bajo **conjuntos de contadores y equipos para supervisar**. Reemplace el texto resaltado escribiendo el nombre del equipo que le gustaría agregar a la lista.  
  
3.  Después de agregar el equipo a la lista, haga clic para expandir la lista de conjuntos de contadores disponibles y, a continuación, haga clic para seleccionar uno o varios de los contadores disponibles se establece para asociar los conjuntos de contadores con el equipo.  
  
4.  Repita los pasos 2 y 3 hasta que se han asociado los conjuntos de contadores a todos los equipos para el que desea recopilar datos de rendimiento.  
  
###  <a name="BKMK_TestSettings"></a> Agregar un archivo de configuración de prueba a la solución para ejecutar pruebas y recopilar datos de forma remota  
 Para configurar la prueba de carga para usar los equipos de Test Controller y Test Agent que creó en [paso 2: configurar el controlador de pruebas de carga y los equipos agente](../technical-guides/step-2-configure-load-test-controller-and-agent-computers.md), siga los pasos de [agregar una configuración de pruebas para la ejecución remota o recopilación de datos a la solución](http://go.microsoft.com/fwlink/?LinkId=209182)(http://go.microsoft.com/fwlink/?LinkId=209182) tal como se indica a continuación:  
  
1.  Para el paso 3, escriba el nombre **BizTalkLoadTest**  
  
2.  Omitir el paso 6 porque ya se ha especificado un nombre en el paso 3.  
  
3.  Paso 7, escriba "Son configuración de pruebas predeterminada para una serie de pruebas remota" en **descripción**.  
  
4.  Paso 8, seleccione el esquema de nomenclatura predeterminado.  
  
5.  Para el paso 9, en **método de ejecución de prueba** seleccione **la ejecución remota de**, en **controlador** seleccione el equipo del controlador de pruebas y deje el resto de las propiedades en el **Roles** página en sus valores predeterminados.  
  
6.  Paso 24, seleccione la opción **a ejecutar en host predeterminado**, seleccione un **hospedar tipo** de **predeterminada**y en **ejecutar pruebas en proceso de bits 32 o 64**, Seleccione la opción de **ejecutar pruebas en proceso de 64 bits en el equipo de 64 bits**.  
  
7.  25 de paso, seleccione **marcar una prueba individual como con errores si su tiempo de ejecución supera** y deje el valor predeterminado de 30 minutos seleccionado.  
  
8.  Paso 27b, active la casilla de verificación para **utilizar el contexto de carga para los ensamblados del directorio de pruebas**y, a continuación, haga clic en **Guardar como**.  
  
9. En el **Guardar como** diálogo cuadro, compruebe que el nombre **BizTalkLoadTest** aparece junto a **nombre de archivo**y haga clic en **guardar**. Ahora ha agregado un archivo de configuración de prueba a la solución.