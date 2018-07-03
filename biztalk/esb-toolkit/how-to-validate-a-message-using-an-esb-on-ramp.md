---
title: 'Cómo: validar un mensaje mediante una rampa de ESB | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43dfc791-7cb6-45a4-898f-f53def199c08
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62df8ec8628353aa127ed6cde8380e5724ddf12a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020572"
---
# <a name="how-to-validate-a-message-using-an-esb-on-ramp"></a>Cómo: validar un mensaje mediante una rampa de ESB
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo configurar el componente de canalización desensamblar distribuidor de ESB para llevar a cabo la validación de mensajes para los mensajes XML enviados a una rampa de ESB.  
  
 En este tema de procedimientos, se completará los pasos siguientes:  
  
-   Crear una rampa de ESB que usa el **ItinerarySelectReceiveXml** canalización.  
  
-   Configurar el componente de canalización desensamblar distribuidor de ESB para validar el contenido del mensaje.  
  
-   Configurar el componente de canalización de Selector de itinerarios para resolver el itinerario adecuado.  
  
-   Validación de mensajes de prueba con un mensaje válido y un mensaje no válido.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema de procedimientos requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="before-you-begin"></a>Antes de comenzar  
 Complete las tareas siguientes antes de realizar los pasos más adelante en este tema de procedimientos:  
  
- Crear un mensaje de prueba no válido.  
  
- Crear un modelo de lenguaje de específicos de dominio (DSL) itinerarios de ESB.  
  
- Configure las propiedades de los itinerarios.  
  
- Definir la estructura de los itinerarios.  
  
- Exporte el modelo a la base de datos de itinerario.  
  
  Los procedimientos siguientes describen cómo realizar cada una de ellas.  
  
#### <a name="to-create-an-invalid-test-message"></a>Para crear un mensaje de prueba no válido  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Crear una copia de NAOrderDoc.xml y, a continuación, cambie el nombre de la copia Invalid.xml.  
  
3.  En el Bloc de notas, abra Invalid.xml.  
  
4.  Cambio **\<ns0:requestType\>10\</ns0:requestType\> a \<ns0:requestType\>diez\</ns0:requestType\>**.  
  
5.  Guardar Invalid.xml como UTF-8 y, a continuación, cierre el Bloc de notas.  
  
    > [!NOTE]
    >  Al cambiar el valor numérico de este elemento en texto, el mensaje ya no será válido de acuerdo con el esquema.  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>Para crear un modelo DSL itinerario de ESB  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en **ItineraryLibrary**, apunte a **agregar**y, a continuación, haga clic en **itinerario nuevo**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, escriba **validación** en el **nombre** cuadro y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>Para configurar las propiedades de los itinerarios  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **Validation.itinerary**. En el **validación** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **exportador de base de datos de itinerario**.  
  
    2.  Haga clic en el botón de puntos suspensivos (...) junto a la **Itinerary Database** propiedad.  
  
    3.  En el **las propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de itinerario del repositorio y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).  
  
2.  En el **estado itinerario** la lista desplegable, haga clic en **implementadas**.  
  
    > [!NOTE]
    >  Este paso le permite exportar el itinerario a un repositorio central; itinerarios pueden seleccionarse y adjunta desde este repositorio cuando se recibe el mensaje. Más adelante, configurará el componente de canalización de Selector de itinerarios para utilizar a una resolución estática para seleccionar el itinerario adecuado desde este repositorio.  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de los itinerarios  
  
1.  En el cuadro de herramientas, arrastre un **vía** elemento de modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **extensor** la lista desplegable, haga clic en **rampa de ESB extensor**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha del elemento de modelo existente. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.  
  
    2.  En el **extensor** la lista desplegable, haga clic en **fuera de rampa ESB extensor**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
3.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento de modelo y la **SendNAOrder** elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  
  
    2.  En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **fuera de rampa extensor**.  
  
    3.  En el **fuera de rampa** desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.  
  
4.  Haga clic en el **resolución** colección de la **SendPortFilter** elemento y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ConfigureOffRamp**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estático**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\Validated%MessageID%.xml**.  
  
5.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **SendPortFilter** elemento de modelo.  
  
6.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendNAOrder** elemento de modelo.  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>Para exportar el modelo a la base de datos de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **validación** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  El itinerario se ha exportado a la base de datos de itinerario y ahora se puede usar el componente de canalización de Selector de itinerarios.  
  
2.  Guarde todos los artefactos de proyecto.  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>Para crear y configurar una rampa de ESB  
  
1.  Haga clic en **iniciar** en la barra de tareas, señale **todos los programas**, apunte a **BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Microsoft.Practices.ESB**.  
  
3.  Haga clic en **ubicaciones de recepción**, apunte a **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
4.  En el **seleccionar un puerto de recepción** cuadro de diálogo, haga clic en **OnRamp.Itinerary**y, a continuación, haga clic en **Aceptar**.  
  
5.  En el **propiedades de ubicación de recepción** cuadro de diálogo, escriba **OnRamp.Itinerary.HowTo** en el **nombre** cuadro.  
  
6.  En el **tipo** la lista desplegable, haga clic en **archivo**y, a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo, escriba **C:\HowTos\DropFolder** en el **carpeta recepción** cuadro y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="to-configure-the-on-ramp-to-perform-message-validation"></a>Para configurar la vía rápida para llevar a cabo la validación de mensajes  
  
1.  En el **propiedades de ubicación de recepción** cuadro de diálogo el **canalización de recepción** la lista desplegable, haga clic en **ItinerarySelectReceiveXml**y, a continuación, haga clic en el botón de puntos suspensivos (...) ).  
  
2.  Use la **configurar canalización** cuadro de diálogo para configurar lo siguiente **desensamblador XML** propiedades de componente:  
  
    1.  Expanda la aplicación GlobalBank.Esb y, a continuación, haga clic en **esquemas**. Haga clic en **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**y, a continuación, haga clic en **propiedades**. Copia el **nombre** y **ensamblado** propiedades y péguelos en un archivo de texto.  
  
    2.  En el **desensamblar** componente, haga clic en **True** en el **ValidateDocument** lista desplegable.  
  
    3.  Haga clic en el **DocumentSpecNames** propiedad y, a continuación, escriba el nombre completo del esquema. El nombre completo comienza con el nombre y va seguido por una coma y la información de ensamblado que se extrajo en el paso una. A continuación se muestra un ejemplo:  
  
         GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc, GlobalBank.ESB.DynamicResolution.Schemas, versión = 2.0.0.0, Culture = neutral, PublicKeyToken = c2c8b2b87f54180a  
  
        > [!NOTE]
        >  Este es el nombre completo del esquema que se valida; se está formado por cuatro propiedades de ensamblado y el nombre de esquema: nombre del ensamblado, versión, referencia cultural y token de clave pública. Se permiten varios valores; Separe varios esquemas con una barra vertical (&#124;) símbolos.  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>Para configurar el componente de canalización de Selector de itinerarios  
  
1.  En el **configurar canalización** diálogo cuadro, configure lo siguiente **itinerario Selector** propiedades de componente:  
  
    1.  Haga clic en el **ItineraryFactKey** propiedad y, a continuación, escriba **Resolver.Itinerary**.  
  
    2.  Haga clic en el **ResolverConnectionString** propiedad y, a continuación, escriba **itinerario:\\\name=Validation;**.  
  
    3.  Haga clic en **Aceptar** para cerrar el **configurar canalización** cuadro de diálogo.  
  
2.  Haga clic en **Aceptar** para cerrar el **propiedades de ubicación de recepción** cuadro de diálogo.  
  
3.  En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
#### <a name="to-test-the-message-validation-and-itinerary-selection"></a>Para probar la selección de itinerario y validación de mensaje  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Copia (no se mueven) NAOrderDoc.xml a la carpeta CarpetaDestino.  
  
3.  Vaya a C:\HowTos\Out. Compruebe que se ha escrito Validated%MessageID%.xml en el directorio.  
  
    > [!NOTE]
    >  El mensaje válido completó su enrutamiento basado en itinerarios, según lo previsto.  
  
4.  Eliminar Validated%MessageID%.xml desde la carpeta Out.  
  
5.  En el Explorador de Windows, vaya a C:\HowTos.  
  
6.  Copia (no se mueven) Invalid.xml a la carpeta CarpetaDestino.  
  
7.  Vaya a C:\HowTos\Out. Compruebe que no se ha entregado ningún mensaje nuevo.  
  
    > [!NOTE]
    >  No se pudo validar el mensaje; por lo tanto, el enrutamiento basado en itinerarios no se pudo completar.  
  
8.  Haga clic en **iniciar** en la barra de tareas, señale **herramientas administrativas**y, a continuación, haga clic en **Visor de eventos**.  
  
9. En el Visor de eventos, expanda **Windows registros**y, a continuación, haga clic en **aplicación**.  
  
10. Busque un evento reciente donde el **origen** es **BizTalk Server**y el **Id. de evento** es **5719**.  
  
    > [!NOTE]
    >  La presentación y el error del mensaje no válido provocó una entrada de excepción en el registro de eventos de aplicación.  
  
11. En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **deshabilitar**.  
  
12. Después de la **OnRamp.Itinerary.HowTo** recibir la ubicación está deshabilitado, haga clic en él y, a continuación, haga clic en **eliminar**. En el **Confirmar eliminación de ubicación de recepción** cuadro de diálogo, haga clic en **Sí**.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: Seleccionar un itinerario mediante una directiva de reglas de negocio](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Instalación y ejecución del ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)