---
title: Utilizar un elemento de Web personalizado con el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b7fecd2-a385-4b2d-a01b-3bfd65ecff3a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37d364f78404b46fe60c705c33247ccb73ba1aa3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964306"
---
# <a name="use-a-custom-web-part-with-the-sap-adapter"></a>Utilizar un elemento de Web personalizado con el adaptador SAP
Esta sección proporciona información sobre el uso de un elemento Web personalizado con Microsoft Office SharePoint Server. Para usar un elemento Web personalizado, debe hacer lo siguiente:  
  
1.  Crear un elemento Web personalizado  
  
2.  Implementar el elemento Web personalizado a un portal de SharePoint  
  
3.  Configurar el portal de SharePoint para usar el elemento Web personalizado  
  
## <a name="before-you-begin"></a>Antes de comenzar  
 Antes de crear un elemento Web personalizado:  
  
-   Publicar los artefactos SAP como un servicio WCF. Para obtener más información, consulte [paso 1: publicar los artefactos de SAP como un servicio WCF](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md) en [Tutorial 1: presentar datos desde un sistema SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).  
  
-   Cree un archivo de definición de aplicación para los artefactos SAP mediante el catálogo de datos empresariales de Microsoft Office SharePoint Server. Para obtener más información, consulte [paso 2: crear un archivo de definición de aplicación para los artefactos de SAP](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md) en [Tutorial 1: presentar datos desde un sistema SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).  
  
##  <a name="Create_a_Custom_Web_Part"></a>Paso 1: Crear un elemento Web personalizado  
 Para crear un elemento Web personalizado con Visual Studio, haga lo siguiente:  
  
1.  Inicie Visual Studio y, a continuación, cree un proyecto.  
  
2.  En el **nuevo proyecto** cuadro de diálogo, desde el **tipos de proyecto** panel, seleccione **Visual C#**. Desde el **plantillas** panel, seleccione **biblioteca de clases**.  
  
3.  Especifique un nombre y una ubicación para la solución. En este tema, especificar `CustomWebPart` en el **nombre** y **nombre de la solución** cuadros. Especifique una ubicación y, a continuación, haga clic en **Aceptar**.  
  
4.  Agregue una referencia al componente System.Web en el proyecto. Haga clic en el nombre del proyecto en **el Explorador de soluciones**y, a continuación, haga clic en **Agregar referencia**. En el **Agregar referencia** cuadro de diálogo, seleccione **System.Web** en el **.NET** ficha y, a continuación, haga clic en **Aceptar**. El componente de System.Web contiene el espacio de nombres necesario de System.Web.UI.WebControls.WebParts.  
  
5.  Agregue el código necesario en función de su problema en el proyecto. Para el ejemplo de código que es relevante para un determinado problema, vea "Problemas que implican elementos Web personalizados" en [consideraciones al utilizar el adaptador SAP con SharePoint](../../adapters-and-accelerators/adapter-sap/considerations-when-using-the-sap-adapter-with-sharepoint.md).  
  
6.  Generar el proyecto. En la compilación correcta del proyecto, se generará un archivo .dll, CustomWebPart.dll, en la \<carpeta de proyecto \> /bin/Debug carpeta.  
  
7.  **Sólo para el equipo de 64 bits**: firmar el archivo CustomWebPart.dll con un nombre seguro antes de realizar los pasos siguientes. En caso contrario, no podrá importar y, por lo tanto, use la CustomWebPart.dll en el portal de SharePoint en "paso 3: configurar el SharePoint Portal para usar el elemento Web personalizado." Vea [Cómo: firmar un ensamblado con un nombre seguro](https://msdn.microsoft.com/library/xc31ft41.aspx).
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a>Paso 2: Implementar el elemento Web personalizado a un SharePoint Portal  
 Debe hacer lo siguiente para que el archivo CustomWebPart.dll (elemento Web personalizado) que se crea en "paso 1: crear un elemento Web personalizado" de este tema se puede usar en el portal de SharePoint:  
  
-   **Copie el archivo CustomWebPart.dll en la carpeta bin de SharePoint Portal**: Microsoft Office SharePoint Server crea portales en el \<root unidad\>: \Inetpub\wwwroot\wss\VirtualDirectories carpeta. Una carpeta se crea para cada portal y puede ser identificada con el número de puerto. Debe copiar el archivo CustomWebPart.dll creado en "paso 1: crear un elemento Web personalizado" de este tema para el \<root unidad\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< númeroDePuerto\>carpeta \bin. Por ejemplo, si el número de puerto de su portal de SharePoint es 13614, debe copiar el archivo CustomWebPart.dll a la \<root unidad\>: \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin carpeta.  
  
    > [!TIP]
    >  Es otra manera de encontrar la ubicación de carpeta de su portal de SharePoint mediante el **Internet Information Services (IIS) Manager** ventana (**iniciar** > **ejecutar**  >  **inetmgr**). Busque su portal de SharePoint en el **Internet Information Services (IIS) Manager** ventana ([NombreDeEquipo] > sitios Web > [nombre del Portal]), menú contextual y, a continuación, haga clic en **propiedades** en el menú contextual. En el cuadro de diálogo Propiedades del portal de SharePoint, haga clic en el **directorio particular** pestaña y, a continuación, seleccione la **ruta de acceso Local** cuadro.  
  
-   **Agregue la entrada de Control seguro en el archivo web.config**: porque se usará el archivo CustomWebPart.dll en equipos diferentes y varios usuarios, debe declarar el archivo como "safe". Para ello, abra el archivo web.config ubicado en la carpeta de portal de SharePoint en \<root unidad\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< númeroDePuerto\>. En la `<SafeControls>` sección del archivo web.config, agregue la siguiente entrada de control seguro:  
  
    -   **En el equipo de 32 bits:**  
  
        ```  
        <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
        ```  
  
    -   **En el equipo de 64 bits:**  
  
        ```  
        <SafeControl Assembly="CustomWebPart, Version=1.0.0.0, Culture=neutral, PublicKeyToken=<PUBLICKKEYTOKEN_OF_CustomWebPart.dll>" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
        ```  
  
     Guarde el archivo web.config y, a continuación, ciérrelo.  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a>Paso 3: Configurar el portal de SharePoint para usar el elemento Web personalizado  
 Debe agregar el elemento Web personalizado para Microsoft Office SharePoint Server Web Part Gallery, por lo que se puede usar en el portal de SharePoint. Para ello:  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre de los servicio proveedor compartidos (SSP) al que desea agregar el elemento Web personalizado.  
  
3.  En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.  
  
4.  En la página Configuración del sitio, haga clic en **elementos Web** en el **galerías** columna.  
  
5.  En la página Galería de elementos Web, para agregar el elemento Web personalizado a la galería, haga clic en **nuevo**. En este punto del elemento Web personalizado no está disponible en la página Galería de elementos Web.  
  
6.  En la página nuevos elementos Web, busque **CustomWebPart** (nombre del elemento Web personalizado) en la lista, active la casilla situada a la izquierda y, a continuación, haga clic en **rellenar galería** en la parte superior de la página. Esto agregará la **CustomWebPart** entrada en la página Galería de elementos Web.  
  
 Ahora puede usar el elemento Web personalizado (**CustomWebPart**) para crear elementos Web en el portal de SharePoint. El elemento Web personalizado (**CustomWebPart**) aparecerán en la **varios** sección en la página Agregar elementos Web.  
  
## <a name="see-also"></a>Vea también  
[Usar el adaptador de SAP con SharePoint](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)