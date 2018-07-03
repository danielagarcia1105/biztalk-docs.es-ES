---
title: Cómo usar un elemento web personalizado con Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf420061-41d1-4d97-9be1-403cd101e41c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83f1dc0b3b46ff8e76ce4dc6dbd9bffd1acdf919
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988245"
---
# <a name="how-to-use-a-custom-web-part-with-oracle-e-business-suite"></a>Cómo usar un elemento web personalizado con Oracle E-Business Suite
Esta sección proporciona información sobre el uso de un elemento Web personalizado con Microsoft Office SharePoint Server. Para usar un elemento Web personalizado, debe hacer lo siguiente:  
  
1.  Crear un elemento Web personalizado  
  
2.  Implementar el elemento Web personalizado en un portal de SharePoint  
  
3.  Configurar el portal de SharePoint para usar el elemento Web personalizado  
  
## <a name="before-you-begin"></a>Antes de comenzar  
 Antes de crear un elemento Web personalizado:  
  
-   Publicar los artefactos de Oracle E-Business Suite como un servicio WCF. Para obtener más información, consulte [paso 1: usar el adaptador de Oracle E-Business para crear y publicar un servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md) en [Tutorial: presentar los datos de Oracle E-Business Suite en un sitio de SharePoint](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).  
  
-   Cree un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite mediante el catálogo de datos empresariales en Microsoft Office SharePoint Server. Para obtener más información, consulte [paso 2: crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md) en [Tutorial: presentar los datos de Oracle E-Business Suite en un sitio de SharePoint](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).  
  
##  <a name="Create_a_Custom_Web_Part"></a> Paso 1: Crear un elemento Web personalizado  
  
1.  Inicie Visual Studio y, a continuación, cree un proyecto.  
  
2.  En el **nuevo proyecto** cuadro de diálogo desde el **tipos de proyecto** panel, seleccione **Visual C#**. Desde el **plantillas** panel, seleccione **biblioteca de clases**.  
  
3.  Especifique un nombre y ubicación de la solución. Este tema, especifique `CustomWebPart` en el **nombre** y **nombre de la solución** cuadros. Especifique una ubicación y, a continuación, haga clic en **Aceptar**.  
  
4.  Agregue una referencia al componente System.Web en el proyecto. Haga clic en el nombre del proyecto en **el Explorador de soluciones**y, a continuación, haga clic en **Agregar referencia**. En el **Agregar referencia** cuadro de diálogo, seleccione **System.Web** en el **.NET** pestaña y, a continuación, haga clic en **Aceptar**. El componente de System.Web contiene el espacio de nombres necesario de System.Web.UI.WebControls.WebParts.  
  
5.  Agregue el código necesario en función de su problema en el proyecto. Para el ejemplo de código que es relevante para un determinado problema, vea "Problemas que implican elementos Web personalizados" en [consideraciones al utilizar el adaptador de Oracle-Business Suite con SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/considerations-using-the-oracle-business-suite-adapter-with-sharepoint.md).  
  
6.  Generar el proyecto. La compilación del proyecto es correcta, se generará un archivo .dll, CustomWebPart.dll, en el \<carpeta del proyecto \> /bin/Debug carpeta.  
  
7.  **Solo para el equipo de 64 bits**: firmar el archivo de CustomWebPart.dll con un nombre seguro antes de realizar los pasos siguientes. En caso contrario, no podrá importar y, por lo tanto, use el CustomWebPart.dll en el portal de SharePoint en "paso 3: configurar el SharePoint Portal para usar el elemento Web personalizado." Para obtener información acerca de cómo firmar un ensamblado con un nombre seguro, vea [Cómo: firmar un ensamblado con un nombre seguro](https://msdn.microsoft.com/library/xc31ft41.aspx).
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a>Paso 2: Implementar el elemento Web personalizado en un Portal de SharePoint  
 Debe hacer lo siguiente para hacer que el archivo CustomWebPart.dll (elemento Web personalizado) que se crea en "paso 1: crear un elemento Web personalizado" de este tema puede usar en el portal de SharePoint:  
  
- **Copie el archivo CustomWebPart.dll en la carpeta bin de SharePoint Portal**: Microsoft Office SharePoint Server crea portales bajo el \<raíz unidad\>: \Inetpub\wwwroot\wss\VirtualDirectories carpeta. Una carpeta se crea para cada portal y puede identificarse con el número de puerto. Debe copiar el archivo CustomWebPart.dll creado en "paso 1: crear un elemento Web personalizado" de este tema para el \<raíz unidad\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< número_puerto\>carpeta \bin. Por ejemplo, si el número de puerto de su portal de SharePoint es 13614, debe copiar el archivo CustomWebPart.dll a la \<raíz unidad\>: carpeta \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin.  
  
  > [!TIP]
  >  Es otra manera de encontrar la ubicación de carpeta de su portal de SharePoint mediante el **Internet Information Services (IIS) Manager** ventana (**iniciar** > **ejecutar**  >  **inetmgr**). Busque su portal de SharePoint en el **Internet Information Services (IIS) Manager** ventana ([NombreDeEquipo] > sitios Web > [nombre-Portal]), con el botón secundario y, a continuación, haga clic en **propiedades** en el menú contextual. En el cuadro de diálogo Propiedades de SharePoint portal, haga clic en el **Home Directory** pestaña y, a continuación, seleccione el **ruta de acceso Local** cuadro.  
  
- **Agregue la entrada de Control seguro en el archivo web.config**: dado que el archivo CustomWebPart.dll se utilizará en equipos diferentes y por varios usuarios, debe declarar el archivo como "seguro". Para ello, abra el archivo web.config ubicado en la carpeta de SharePoint portal en \<raíz unidad\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< número_puerto\>. En la `<SafeControls>` sección del archivo web.config, agregue la siguiente entrada de control segura:  
  
  - **En el equipo de 32 bits:**  
  
    ```  
    <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
  - **En el equipo de 64 bits:**  
  
    ```  
    <SafeControl Assembly="CustomWebPart, Version=1.0.0.0, Culture=neutral, PublicKeyToken=<PUBLICKKEYTOKEN_OF_CustomWebPart.dll>" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
    Guarde el archivo web.config y, a continuación, ciérrelo.  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a>Paso 3: Configurar el portal de SharePoint para usar el elemento Web personalizado  
 Deberá agregar el elemento Web personalizado para Microsoft Office SharePoint Server Web Part Gallery, por lo que se puede usar en el portal de SharePoint. Para ello:  
  
1. Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft Office Server**y, a continuación, haga clic en **SharePoint 3.0 Central Administration**.  
  
2. En el panel de navegación izquierdo, haga clic en el nombre del servicio de proveedor compartidos (SSP) al que desea agregar el elemento Web personalizado.  
  
3. En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.  
  
4. En la página Configuración del sitio, haga clic en **elementos Web** bajo el **galerías** columna.  
  
5. En la página Galería de elementos Web, para agregar el elemento Web personalizado a la galería, haga clic en **New**. En este momento, el elemento Web personalizado no está disponible en la página Galería de elementos Web.  
  
6. En la página nuevos elementos Web, busque **CustomWebPart** (nombre del elemento Web personalizado) en la lista, seleccione la casilla situada a la izquierda y, a continuación, haga clic en **rellenar galería** en la parte superior de la página. Esto agregará la **CustomWebPart** entrada en la página Galería de elementos Web.  
  
   Ahora puede usar el elemento Web personalizado (**CustomWebPart**) para crear elementos Web en el portal de SharePoint. El elemento Web personalizado (**CustomWebPart**) aparecerá bajo la **varios** sección en la página Agregar elementos Web.  
  
## <a name="see-also"></a>Vea también  
[Usar el adaptador de Oracle E-Business Suite con SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)