---
title: 'Cómo: convertir un documento de texto en XML y enrutarlo a una ubicación de archivo con una lista de distribución de itinerarios | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01597a5f-5ca3-440e-ad97-70332233f319
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e6690af0cd326853fc0f96254aaaf7083ccd15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982573"
---
# <a name="how-to-convert-a-text-document-to-xml-and-route-to-a-file-location-using-an-itinerary-routing-slip"></a>Cómo: convertir un documento de texto en XML y enrutarlo a una ubicación de archivo con una lista de distribución de itinerarios
## <a name="goal"></a>Objetivo  
 La sección muestra cómo crear una canalización que convertir un documento de texto en XML y, a continuación, seleccione el itinerario adecuado y enrutar el mensaje a una ubicación de archivo.  
  
 En este tema de procedimientos, se completará los pasos siguientes:  
  
-   Use una canalización para recibir un documento de archivo sin formato y convertirlo a XML.  
  
-   Configurar el componente de canalización de Selector de itinerarios para resolver la lista de distribución adecuada.  
  
-   Cree una vía rápida que utiliza la canalización personalizada.  
  
-   Probar el enrutamiento basado en itinerarios de un mensaje de archivo sin formato.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema de procedimientos requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="before-you-begin"></a>Antes de comenzar  
 Complete las tareas siguientes antes de realizar los pasos más adelante en este tema de procedimientos:  
  
- Implementar el **DataFormatTransformation** itinerario.  
  
- Crear el mensaje de prueba.  
  
  Los procedimientos siguientes describen cómo realizar cada una de ellas.  
  
#### <a name="to-deploy-the-dataformattransformation-itinerary"></a>Para implementar el itinerario DataFormatTransformation  
  
1.  En Visual Studio, abra C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln.  
  
2.  En el Explorador de soluciones, en el **Itinerary.Library** del proyecto, haga doble clic en **DataFormatTransformation.itinerary** para abrirlo en el Diseñador de itinerario.  
  
3.  En Visual Studio, haga clic en la superficie de diseño de **DataFormatTransformation.itinerary**. En el **DataFormatTransformation.itinerary** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **estado itinerario** la lista desplegable, haga clic en **implementadas**.  
  
    2.  En el **modelo exportador** la lista desplegable, haga clic en **exportador de base de datos de itinerario**.  
  
    3.  Haga clic en el botón de puntos suspensivos (...) junto a la **Itinerary Database** propiedad.  
  
    4.  En el **las propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de itinerario del repositorio y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).  
  
4.  Guarde todos los artefactos de proyecto.  
  
5.  En Visual Studio, haga clic en la superficie de diseño de la **DataModelTransformation** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
#### <a name="to-create-the-receive-pipeline"></a>Para crear la canalización de recepción  
  
1.  En Visual Studio, haga clic en **DataFormatTransformation.Schemas**y, a continuación, haga clic en **propiedades**. Haga clic en **aplicación**y, a continuación, escriba **GlobalBank.ESB.DataFormatTransformation.Schemas** en el **nombre del ensamblado** cuadro.  
  
2.  Haga clic en **DataFormatTransformation.Schemas**y, a continuación, haga clic en **propiedades**. Haga clic en **firma**y, a continuación, compruebe que la **firmar el ensamblado** casilla está activada y que señala la ubicación del ensamblado **.\\... \\.. \\.. \\.. \\.. \keys\Microsoft.Practices.ESB.snk**.  
  
3.  Haga clic en **DataFormatTransformation.Pipelines**y, a continuación, haga clic en **quitar**.  
  
4.  Haga clic en **DataFormatTransformation**, apunte a **agregar**y, a continuación, haga clic en **nuevo proyecto**. Haga clic en **proyectos de Biztalk**y, a continuación, haga clic en **proyecto vacío de servidor Biztalk**. En el **nombre** , escriba **DataFormatTransformationReceive.Pipeline**.  
  
5.  Haga clic en **DataFormatTransformationReceive.Pipeline**y, a continuación, haga clic en **propiedades**. Haga clic en **firma**y, a continuación, compruebe que la **firmar el ensamblado** casilla está activada y que señala la ubicación del ensamblado **C:\projects\Microsoft.Practices.ESB\keys\ Microsoft.Practices.ESB.snk**.  
  
6.  Haga clic en **DataFormatTransformationReceive.Pipeline**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
7.  En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **canalización de recepción** en el panel Plantillas. En el **nombre** , escriba **ItinerarySelectReceiveFF**y, a continuación, haga clic en **agregar**.  
  
8.  Haga clic en **referencias** para el proyecto DataFormatTransformationReceive.Pipeline y, a continuación, haga clic en **Agregar referencia**. Haga clic en el **proyectos** pestaña y, a continuación, haga clic en **DataFormatTransformation.Schemas**. Haga clic en **Aceptar** para agregar la referencia.  
  
9. En el cuadro de herramientas, arrastre un **Desensamblador de archivos** componente de canalización para la **desensamblar** fase de la canalización.  
  
10. En la ventana de propiedades del archivo plano de desensamblado, haga clic en **DataModelTransformation.Schemas.NAOrderDocFF** en el **esquema de documento** lista desplegable.  
  
11. En el cuadro de herramientas, arrastre un **Selector de itinerarios de ESB** componente de canalización para la **resolver entidad** fase de la canalización.  
  
12. En el cuadro de herramientas, arrastre un **distribuidor de ESB** componente de canalización para la **resolver entidad** fase de la canalización y, a continuación, colóquelo bajo el **Selector de itinerarios de ESB** canalización componente.  
  
13. Guarde todos los artefactos de proyecto.  
  
## <a name="to-create-the-test-message"></a>Para crear el mensaje de prueba  
  
1.  Haga clic una vez en el archivo de esquema NAOrderDocFF.xsd del proyecto DataFormatTransformation.Schemas. En el panel de propiedades de Visual Studio, cambie las dos propiedades siguientes:  
  
    -   **Genere el tipo de salida de instancia**. Haga clic en la lista desplegable Cambiar a esta propiedad **nativo**.  
  
    -   **Nombre de archivo de instancia de salida**. Haga clic en el botón de puntos suspensivos (...) para esta propiedad y acepte la ruta de acceso predeterminada de C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation. En el **nombre de archivo** , escriba **NAOrderDocFF**y, a continuación, haga clic en **guardar**.  
  
2.  Haga clic en **NAOrderDocFF.xsd** en **DataFormatTransformation.Schemas**y, a continuación, haga clic en **generar instancia**. En este momento, debe tener un nuevo archivo que se genera en el directorio C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation.  
  
3.  Copia (sin mover) el archivo NAOrderDocFF.txt desde C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation a C:\HowTos.  
  
    > [!NOTE]
    >  Este es el mensaje que recibirá y la convierte a XML. En este documento representa una versión de archivo sin formato de documento de pedido de América del Norte.  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-deploy-the-receive-pipeline-and-the-schema"></a>Para implementar la canalización de recepción y el esquema  
  
1.  Haga clic en **DataFormatTransformationReceive.Pipeline**y, a continuación, haga clic en **propiedades**. Haga clic en **implementación**y, a continuación, escriba **Microsoft.Practices.ESB** en el **nombre de la aplicación** cuadro.  
  
2.  Haga clic en el **DataFormatTransformation.Schemas** del proyecto y, a continuación, haga clic en **propiedades**. Haga clic en **implementación**y, a continuación, escriba **Microsoft.Practices.ESB** en el **nombre de la aplicación** cuadro.  
  
3.  Cerrar los paneles de propiedades para ambos **DataFormatTransformationReceive.Pipeline** y **DataFormatTransformation.Schemas**.  
  
4.  En el Explorador de soluciones, haga clic en el **DataFormatTransformation** del proyecto y, a continuación, haga clic en **implementar solución**.  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>Para crear y configurar una rampa de ESB  
  
1.  Haga clic en **iniciar** en la barra de tareas, señale **todos los programas**, apunte a **BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, haga clic en **Microsoft.Practices.ESB**.  
  
3.  Haga clic en **ubicaciones de recepción**, apunte a **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
4.  En el **seleccionar un puerto de recepción** cuadro de diálogo, haga clic en **OnRamp.Itinerary**y, a continuación, haga clic en **Aceptar**.  
  
5.  En el **propiedades de ubicación de recepción** cuadro de diálogo el **nombre** , escriba **OnRamp.Itinerary.FlatFile.FILE**.  
  
6.  En el **tipo** la lista desplegable, haga clic en **archivo**y, a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo el **carpetas de recepción** , escriba **C:\HowTos\DropFolder**.  
  
8.  En el **propiedades de transporte de archivo** cuadro de diálogo el **máscara de archivo** , escriba  **\*.txt**y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>Para configurar el componente de canalización de Selector de itinerarios  
  
1.  En el **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **ItinerarySelectReceiveFF** en el **canalización de recepción** lista desplegable y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
2.  Use la **configurar canalización** cuadro de diálogo para configurar lo siguiente **itinerario Selector** propiedades de componente:  
  
    1.  Haga clic en el **ItineraryFactKey** propiedad y, a continuación, escriba **Resolver.Itinerary**.  
  
    2.  Haga clic en el **ResolverConnectionString** propiedad, tipo **itinerario:\\\name=DataFormatTransformation;** y, a continuación, haga clic en **Aceptar**.  
  
3.  Haga clic en **Aceptar** para cerrar el **propiedades de ubicación de recepción** cuadro de diálogo.  
  
4.  En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.FlatFile.FILE** ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
#### <a name="to-test-itinerary-based-routing-of-a-flat-file-message"></a>Para probar el enrutamiento basado en itinerarios de un mensaje de archivo sin formato  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Copia (no se mueven) NAOrderDocFF.txt a C:\HowTos\DropFolder.  
  
3.  Vaya a C:\HowTos\Out. Compruebe que se ha escrito el mensaje DFT%MessageID%.xml en el directorio.  
  
4.  En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.FlatFile.FILE** ubicación de recepción y, a continuación, haga clic en **deshabilitar**.  
  
5.  Después de la **OnRamp.Itinerary.FlatFile.FILE** recibir la ubicación está deshabilitado, haga clic en él y, a continuación, haga clic en **eliminar**. En el **Confirmar eliminación de ubicación de recepción** cuadro de diálogo, haga clic en **Sí**.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: Transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución de itinerarios](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [Cómo: Enrutar un solo mensaje a varios destinatarios mediante una lista de distribución de itinerarios](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Patrones de transformación de mensajes](../esb-toolkit/message-transformation-patterns.md)