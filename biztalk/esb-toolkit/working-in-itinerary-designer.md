---
title: Trabajar en el Diseñador de itinerarios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06742cb8-f6d6-46e2-adc0-6be9a3d6a447
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf474c68d91b7648f7f0efcfe4e85e7531e4aa1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976786"
---
# <a name="working-in-itinerary-designer"></a>Trabajar en el Diseñador de itinerarios
Después de crear un proyecto de Microsoft Visual C#, puede crear nuevos modelos itinerarios y agregar itinerarios existentes al proyecto. Los pasos siguientes describen cómo crear un nuevo itinerario, agregar un modelo de itinerarios existente o cambiar el nombre de un itinerario.  
  
> [!NOTE]
>  Antes de trabajar con el Diseñador de itinerario, debe instalar Microsoft.Practices.ESB.CORE Windows Installer (archivo .msi) desde el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] la carpeta de instalación. Este paso instala a los ensamblados de tiempo de ejecución necesarios a la caché global de ensamblados.  
  
## <a name="basic-operations"></a>Operaciones básicas  

#### <a name="create-an-itinerary"></a>Crear un itinerario  
  
1.  En el Explorador de soluciones, haga clic en el nombre del proyecto de C#, seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
2.  En el **nombre** en la parte inferior del cuadro de diálogo, escriba el nombre para el itinerario y, a continuación, haga clic en **agregar**.  
  
    > [!NOTE]
    >  Se crea y se muestra en el Diseñador de itinerario el itinerario nueva, y se crea un archivo .itinerary correspondiente y se muestra en el Explorador de soluciones.  
  
#### <a name="add-an-existing-itinerary-to-the-project"></a>Agregue un itinerario existente al proyecto
  
1.  En el Explorador de soluciones, haga clic con el nombre del proyecto de C#, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.  
  
2.  En el **Agregar elemento existente** cuadro de diálogo, desplácese al directorio que contiene los itinerarios, haga clic en el itinerario y, a continuación, haga clic en **agregar**.  
  
    > [!NOTE]
    >  El itinerario se agrega al proyecto.  
  
#### <a name="change-the-name-of-an-itinerary"></a>Cambiar el nombre de un itinerario  
  
1.  En el Explorador de soluciones, haga clic en el archivo .itinerary que desea cambiar y, a continuación, haga clic en **cambiar el nombre de**.  
  
2.  Escriba el nuevo nombre de archivo y, a continuación, presione ENTRAR.  
  
#### <a name="save-an-itinerary"></a>Guardar un itinerario  
  
En el **archivo** menú, haga clic en **guardar \<nombre itinerario\>**.  
  
> [!NOTE]
>  Archivos itinerarios se guardan como modelos DSL en formato XML correspondiente.  
  
#### <a name="set-itinerary-export-properties"></a>Establecer las propiedades de exportación itinerarios  
  
1.  En la ventana Propiedades, escriba un **nombre** propiedad.  
  
2.  En la ventana Propiedades, escriba un **versión** propiedad.  
  
3.  En la ventana Propiedades, especifique la **es la respuesta de solicitud** propiedad mediante la lista desplegable. Establezca esta propiedad en **true** si el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] aplicación cliente se comunica con un aumento con el patrón de intercambio de mensajes de solicitud y respuesta.  
  
4.  En la ventana Propiedades, establezca la **exportar modo** propiedad **predeterminado** o **Strict**.  
  
    > [!NOTE]
    >  Al crear [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerarios utilizando el Diseñador de itinerario, el **exportar modo** propiedad puede utilizarse para definir dónde se ejecutará el servicio. Establecer el **exportar modo** propiedad **Strict** garantiza que el itinerario servicio se ejecuta en su contenedor prescrita; en este caso, cada servicio itinerario en el itinerario XML tiene una propiedad de la fase que Especifica la canalización en el que se ejecuta el servicio. Si esta propiedad se establece en **predeterminado**, se crea un itinerario compatible con Microsoft ESB, con ninguna fase especificada, y el servicio itinerario se ejecuta en el orden establecido, pero no necesariamente en la fase de canalización deseado.  
  
#### <a name="export-an-itinerary-to-a-file"></a>Exportar un itinerario a un archivo  
  
1.  En la ventana Propiedades, haga clic en **XML itinerario exportador** en el **modelo exportador** lista desplegable.  
  
2.  En la ventana Propiedades, establezca la **archivo XML de itinerario** propiedad a un nuevo valor.  
  
#### <a name="export-an-itinerary-to-a-database"></a>Exportar un itinerario a una base de datos  
  
1.  En la ventana Propiedades, haga clic en **base de datos de itinerario exportador** en el **modelo exportador** lista desplegable.  
  
2.  En la ventana Propiedades, establezca la **base de datos de itinerario** cadena de conexión de la propiedad para que apunte a la base de datos de itinerario.  
  
3.  En la ventana Propiedades, establezca la **estado de itinerario** propiedad **publicada** o **implementadas**.  
  
    > [!NOTE]
    >  Cuando se exporta un itinerario para una base de datos con **estado de itinerario** establecido en **publicada**, el itinerarios no son eficaces para el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] tiempo hasta el de ejecución después de que la propiedad se establece en  **Implementar**.  
  
## <a name="security-operations"></a>Operaciones de seguridad  
 Mediante el Diseñador de itinerario, puede proteger información confidencial, como contraseñas y otras credenciales se almacenan en un [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerarios, mediante el cifrado de esta información utilizando certificados X.509.  
  
#### <a name="select-the-x509-certificate-for-an-itinerary"></a>Seleccione el certificado X.509 para un itinerario  
  
1.  En la ventana Propiedades del Diseñador de itinerario, expanda la **certificado de cifrado** propiedad y, a continuación, haga clic en el **ubicación del almacén de** lista desplegable y seleccione el **CurrentUser**o **LocalMachine**. Esto asocia el almacén de certificados X.509 con el usuario actual o el equipo local.  
  
2.  En la ventana Propiedades, haga clic en el **almacenar nombre** lista desplegable y seleccione el valor que se corresponde con el almacén de certificados.  
  
3.  En la ventana Propiedades, haga clic en el botón de puntos suspensivos (...) junto a la propiedad de certificado de cifrado y, a continuación, seleccione la **certificado X.509** en el **Seleccionar certificado** cuadro de diálogo.  
  
#### <a name="remove-the-x509-certificate-from-an-itinerary"></a>Quitar el certificado X.509 de un itinerario  
  
-   En la ventana Propiedades del Diseñador de itinerario, expanda la **certificado de cifrado** propiedad y, a continuación, establezca el **ubicación del almacén de** propiedad en un valor diferente. Esto desasocia el certificado antiguo con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] modelo itinerario.  
  
#### <a name="disable-the-x509-certificate-validation"></a>Deshabilitar la validación del certificado X.509  
  
En el Editor del registro, vaya a la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**y, a continuación, establezca el **RequireX509Certificate** valor de propiedad  **false**.  
  
> [!NOTE]
>  Si instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] en un sistema operativo que tenga compatibilidad con 64 bits, la subclave es **HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**.