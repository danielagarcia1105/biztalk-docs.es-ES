---
title: 'Cómo: habilitar el seguimiento de BAM en un servicio de itinerarios de ESB | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58859937-f8d0-4c33-9a7a-62fec8441936
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27d0338ad56daa342fce1d339b9e7aa43fd7e25e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991549"
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a>Cómo: habilitar el seguimiento de BAM en un servicio de itinerarios de ESB
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo habilitar el Monitor de actividad de negocio (BAM) de seguimiento para un itinerario existente.  
  
 En este tema de procedimientos, se completará los pasos siguientes:  
  
-   Habilitar la propiedad que se utiliza para realizar el seguimiento de los servicios de itinerario mediante el Monitor de actividad de negocio.  
  
-   Seguimiento de BAM mediante la aplicación de ejemplo de cliente de prueba de itinerario de pruebas.  
  
-   Compruebe los resultados BAM mediante una consulta SQL.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema de procedimientos requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="before-you-begin"></a>Antes de comenzar  
 Complete las tareas siguientes antes de realizar los pasos más adelante en este tema de procedimientos:  
  
- Crear un modelo de lenguaje de específicos de dominio (DSL) itinerarios de ESB.  
  
- Configure las propiedades de los itinerarios.  
  
- Definir la estructura de los itinerarios.  
  
  Los procedimientos siguientes describen cómo realizar cada una de ellas.  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>Para crear un modelo DSL itinerario de ESB  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nuevo**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **ItineraryDsl** en el panel Plantillas.  
  
4.  En el **nombre** , escriba **BamTracking**y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>Para configurar las propiedades de los itinerarios  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **BamTracking.itinerary**. En el **BamTracking** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  
  
    2.  En el **configuración extensor** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).  
  
    3.  En el **Seleccionar archivo XML** cuadro de diálogo el **nombre de archivo** , escriba **C:\HowTos\Itineraries\BamTracking** y, a continuación, haga clic en **guardar**.  
  
        > [!NOTE]
        >  Este paso le permite exportar el itinerario como XML en una ubicación de archivos local. Exportando un itinerario en una ubicación de archivos local, en lugar de a la base de datos de itinerario, permite probar el itinerario mediante la aplicación cliente de prueba de ESB. Complete este proceso más adelante en este tema de procedimientos.  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de los itinerarios  
  
1.  En el cuadro de herramientas, arrastre un **vía** elemento de modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **extensor** la lista desplegable, haga clic en **extensión de servicio de rampa de ESB**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **vía** elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **MapNAOrderToCNOrder**.  
  
    2.  En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **extensión de servicio de itinerarios de mensajería**.  
  
        > [!NOTE]
        >  Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería). Como alternativa, si el proceso llevará a cabo en una orquestación, establezca el **extensor del servicio de itinerarios** propiedad **extensión de servicio de itinerario de orquestación**.  
  
    3.  En el **contenedor** desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **Service Name** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Transform**.  
  
3.  Haga clic en el **resolución** colección de la **MapNAOrderToCNOrder** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticallySpecifyTheMap**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estático**.  
  
    3.  En el **transformar tipo** la lista desplegable, haga clic en **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.  
  
    4.  En el **TransportName** la lista desplegable, haga clic en **archivo**.  
  
4.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **MapNAOrderToCNOrder** elemento de modelo.  
  
5.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **MapNAOrderToCNOrder** elemento de modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendCNOrder**.  
  
    2.  En el **extensor** la lista desplegable, haga clic en **extensión de servicio fuera de rampa ESB**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
6.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **MapNAOrderToCNOrder** elemento de modelo y la **SendCNOrder**elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  
  
    2.  En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **extensión de servicio fuera de rampa itinerario**.  
  
    3.  En el **fuera de rampa** desplegable lista, expanda **SendCNOrder**y, a continuación, haga clic en **controladores de envío**.  
  
7.  Haga clic en el **resolución** colección de la **SendPortFilter** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ConfigureFolderSettings**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estático**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\BAM%MessageID%.xml**  
  
        > [!NOTE]
        >  Cada fuera de rampa tendrá un servicio de itinerarios asociado; la combinación de las propiedades del servicio de itinerarios y las propiedades de fuera de rampa define la suscripción del puerto de envío dinámico.  
  
8.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **MapNAOrderToCNOrder** elemento de modelo para el **SendPortFilter** elemento de modelo.  
  
9. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendCNOrder** elemento de modelo.  
  
10. Guarde todos los artefactos de proyecto.  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-modify-the-itinerary"></a>Para modificar el itinerario  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga doble clic en **BamTracking.itinerary**.  
  
3.  Haga clic en el **MapNAOrderToCNOrder** elemento de servicio de itinerarios.  
  
4.  En el **MapNAOrderToCNOrder** ventana Propiedades, haga clic en **True** en el **seguimiento habilitado** lista desplegable.  
  
5.  Haga clic en el **SendPortFilter** elemento de servicio de itinerarios.  
  
6.  En el **SendPortFilter** ventana Propiedades, haga clic en **True** en el **seguimiento habilitado** lista desplegable.  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>Para exportar el modelo para su uso con el cliente de prueba de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **BamTracking** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  
  
2.  Guarde todos los artefactos de proyecto.  
  
3.  En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (BamTracking.xml).  
  
#### <a name="to-test-the-itinerary"></a>Para probar el itinerario  
  
1.  Abra la aplicación de ejemplo de cliente de prueba de itinerario mediante el acceso directo que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  
  
2.  En el cliente de prueba de itinerario, desactive la **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.  
  
3.  En el **abrir archivo itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries. Seleccione **BamTracking.xml**y, a continuación, haga clic en **abierto** para cargar el itinerario.  
  
4.  Haga clic en **Aceptar** para borrar el **itinerario se cargó correctamente** mensaje.  
  
5.  En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **carga mensaje** cuadro.  
  
6.  En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos. Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abierto** para cargar el mensaje de prueba.  
  
7.  Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.  
  
8.  En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se ha escrito el mensaje BAM%MessageID%.xml en el directorio.  
  
#### <a name="to-verify-message-tracking"></a>Para comprobar el seguimiento de mensajes  
  
1. Haga clic en **iniciar** en la barra de tareas, señale **todos los programas**, apunte a [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2. Haga clic en **Nueva consulta**.  
  
3. En el panel consulta, escriba lo siguiente:  
  
   ```  
   SELECT *  
   FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
   GO  
   ```  
  
4. Haga clic en **Ejecutar**.  
  
5. En el panel de resultados, utilice el **TimeStamp** columna para buscar la entrada más reciente.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Patrones de enrutamiento de mensajes](../esb-toolkit/message-routing-patterns.md)  
  
-   [Uso de resolución y enrutamiento dinámicos](../esb-toolkit/using-dynamic-resolution-and-routing.md)