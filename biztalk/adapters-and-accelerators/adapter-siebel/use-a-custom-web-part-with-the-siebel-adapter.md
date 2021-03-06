---
title: Use el elemento Web personalizado con el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3a6c04-6523-483c-bdf4-ce0ac47cda87
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b8843a3336c6cec17120bef109aa5119509aed9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999765"
---
# <a name="use-a-custom-web-part-with-the-siebel-adapter"></a>Use el elemento Web personalizado con el adaptador de Siebel
Esta sección proporciona información sobre el uso de un elemento Web personalizado con Microsoft Office SharePoint Server. Para usar un elemento Web personalizado, debe hacer lo siguiente:  
  
1.  Crear un elemento Web personalizado  
  
2.  Implementar el elemento Web personalizado en un portal de SharePoint  
  
3.  Configurar el portal de SharePoint para usar el elemento Web personalizado  
  
## <a name="before-you-begin"></a>Antes de comenzar  
 Antes de crear un elemento Web personalizado:  
  
-   Publicar los artefactos de Siebel como un servicio WCF. Para obtener más información, consulte [paso 1: publicar las operaciones de componentes empresariales de Siebel como un servicio WCF](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md) en [Tutorial 1: presentación de datos de sistema de Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).  
  
-   Cree un archivo de definición de aplicación para los artefactos de Siebel mediante el catálogo de datos empresariales en Microsoft Office SharePoint Server. Para obtener más información, consulte [paso 2: crear un archivo de definición de aplicación para operaciones de componentes empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md) en [Tutorial 1: presentación de datos de sistema de Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).  
  
##  <a name="Create_a_Custom_Web_Part"></a> Paso 1: Crear un elemento Web personalizado  
 Para crear un elemento Web personalizado con Visual Studio, haga lo siguiente:  
  
1.  Inicie Visual Studio y, a continuación, cree un proyecto.  
  
2.  En el **nuevo proyecto** cuadro de diálogo desde el **tipos de proyecto** panel, seleccione **Visual C#**. Desde el **plantillas** panel, seleccione **biblioteca de clases**.  
  
3.  Especifique un nombre y ubicación de la solución. Este tema, especifique `CustomWebPart` en el **nombre** y **nombre de la solución** cuadros. Especifique una ubicación y, a continuación, haga clic en **Aceptar**.  
  
4.  Agregue una referencia al componente System.Web en el proyecto. Haga clic en el nombre del proyecto en **el Explorador de soluciones**y, a continuación, haga clic en **Agregar referencia**. En el **Agregar referencia** cuadro de diálogo, seleccione **System.Web** en el **.NET** pestaña y, a continuación, haga clic en **Aceptar**. El componente de System.Web contiene el espacio de nombres necesario de System.Web.UI.WebControls.WebParts.  
  
5.  Agregue el código necesario en función de su problema en el proyecto. Para el ejemplo de código que es relevante para un determinado problema, vea "Problemas que implican elementos Web personalizados" en [consideraciones al usar el adaptador de Siebel con SharePoint](../../adapters-and-accelerators/adapter-siebel/considerations-when-using-the-siebel-adapter-with-sharepoint.md).  
  
6.  Generar el proyecto. La compilación del proyecto es correcta, se generará un archivo .dll, CustomWebPart.dll, en el \< *carpeta del proyecto* \> /bin/Debug carpeta.  
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a>Paso 2: Implementar el elemento Web personalizado en un Portal de SharePoint  
 Debe hacer lo siguiente para hacer que el archivo CustomWebPart.dll (elemento Web personalizado) que se crea en "paso 1: crear un elemento Web personalizado" de este tema puede usar en el portal de SharePoint:  
  
-   **Copie el archivo CustomWebPart.dll en la carpeta bin de SharePoint Portal**: Microsoft Office SharePoint Server crea portales bajo el \< *raíz unidad*\>: \Inetpub\wwwroot\wss\ Carpeta VirtualDirectories. Una carpeta se crea para cada portal y puede identificarse con el número de puerto. Debe copiar el archivo CustomWebPart.dll creado en "paso 1: crear un elemento Web personalizado" de este tema para el \< *raíz unidad*\>: \Inetpub\wwwroot\wss\VirtualDirectories\\ < *Port_Number*\>carpeta \bin. Por ejemplo, si el número de puerto de su portal de SharePoint es 13614, debe copiar el archivo CustomWebPart.dll a la \< *raíz unidad*\>: carpeta \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin.  
  
    > [!TIP]
    >  Es otra manera de encontrar la ubicación de carpeta de su portal de SharePoint mediante el **Internet Information Services (IIS) Manager** ventana (**iniciar** > **ejecutar**  >  **inetmgr**). Busque su portal de SharePoint en el **Internet Information Services (IIS) Manager** ventana ([*computer_name*] > sitios Web > [*Portal-Name*]), con el botón secundario, y a continuación, haga clic en **propiedades** en el menú contextual. En el cuadro de diálogo Propiedades de SharePoint portal, haga clic en el **Home Directory** pestaña y, a continuación, seleccione el **ruta de acceso Local** cuadro.  
  
-   **Agregue la entrada de Control seguro en el archivo web.config**: dado que el archivo CustomWebPart.dll se utilizará en equipos diferentes y por varios usuarios, debe declarar el archivo como "seguro". Para ello, abra el archivo web.config ubicado en la carpeta de SharePoint portal en \< *raíz unidad*\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< número_puerto\>. En la `<SafeControls>` sección del archivo web.config, agregue la siguiente entrada de control segura:  
  
    ```  
    <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
     Guarde el archivo web.config y, a continuación, ciérrelo.  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a>Paso 3: Configurar el Portal de SharePoint para usar el elemento Web personalizado  
 Deberá agregar el elemento Web personalizado para Microsoft Office SharePoint Server Web Part Gallery, por lo que se puede usar en el portal de SharePoint. Para ello:  
  
1. Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft Office Server**y, a continuación, haga clic en **SharePoint 3.0 Central Administration**.  
  
2. En el panel de navegación izquierdo, haga clic en el nombre de los servicios de proveedor compartidos (SSP) al que desea agregar el elemento Web personalizado.  
  
3. En el **administración de servicios compartidos** , en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.  
  
4. En el **configuración del sitio** página, haga clic en **elementos Web** bajo el **galerías** columna.  
  
5. En el **Galería de elementos Web** , para agregar el elemento Web personalizado a la galería, haga clic en **New**. En este momento no está disponible en el elemento Web personalizado la **Galería de elementos Web** página.  
  
6. En el **nuevos elementos Web** página, busque **CustomWebPart** (nombre del elemento Web personalizado) en la lista, seleccione la casilla situada a la izquierda y, a continuación, haga clic en **rellenar galería** en la parte superior de la página. Esto agregará la **CustomWebPart** entrada en el **Galería de elementos Web** página.  
  
   Ahora puede usar el elemento Web personalizado (**CustomWebPart**) para crear elementos Web en el portal de SharePoint. El elemento Web personalizado (**CustomWebPart**) aparecerá bajo la **varios** sección la **agregar elementos Web** página.  
  
## <a name="see-also"></a>Vea también  
 [Usar el adaptador de Siebel con SharePoint](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)