---
title: Cómo modificar las opciones de implementación de un ensamblado de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, deploying
- managing [assemblies], modifying
- deploying, assemblies
- managing [assemblies], deploying
- assemblies, deploying
ms.assetid: d25e2f71-08bd-4786-ab6c-35ae4e88b8cc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16ba9dc20893a2899f7fbed78aefb3d1a0bcfdb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973589"
---
# <a name="how-to-modify-the-deployment-options-of-a-biztalk-assembly"></a>Cómo modificar las opciones de implementación de un ensamblado de BizTalk
En este tema se describe cómo usar la consola de administración de BizTalk Server para modificar las opciones de implementación de un ensamblado de BizTalk.  
  
 Puede especificar las siguientes opciones de implementación:  
  
-   **Agregar a la caché global de ensamblados de agregar recursos (gacutil).** al activar esta opción, el ensamblado se agrega a la caché de ensamblados global (GAC) en el equipo local cuando el ensamblado se agrega a la aplicación. Además, si actualiza posteriormente el ensamblado (haga clic en él y haga clic en **actualizar**), el ensamblado se agrega a la GAC. Al desactivar la casilla de verificación de esta opción, el ensamblado no se quita de la GAC si actualmente existe en dicho lugar.  
  
-   **Agregar a la caché global de ensamblados en la importación de archivo MSI (gacutil).** instala el ensamblado en la GAC del equipo local cuando se importa el archivo .msi de la aplicación.  
  
-   **Agregar a la caché global de ensamblados en la instalación de archivos MSI (gacutil).** instala el ensamblado en la GAC del equipo local cuando se instala la aplicación desde el archivo .msi.  
  
-   **Ubicación de destino:** ruta de acceso a la que se copiará el archivo de ensamblado cuando se instala la aplicación. Si no se proporciona una ruta, el archivo de ensamblado no se copiará en el sistema de archivos local durante la instalación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Además, si selecciona una opción que agrega inmediatamente el ensamblado a la GAC, la cuenta debe pertenecer también al grupo de administradores local. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-modify-the-deployment-options-of-a-biztalk-assembly"></a>Para modificar las opciones de implementación de un ensamblado de BizTalk  
  
1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk que contiene el ensamblado de BizTalk que se va a modificar las opciones de implementación y, a continuación, expanda la aplicación que contiene el ensamblado de BizTalk.  
  
3. Haga clic en el **recursos** carpeta, haga clic en el ensamblado de BizTalk y, a continuación, haga clic en **modificar**.  
  
4. En **opciones**, active las casillas de las opciones de implementación que desee.  
  
5. Si es necesario, en **ubicación de destino** editar la ruta de acceso donde se copiará cuando la aplicación se instala el ensamblado y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de ensamblados de BizTalk](../core/managing-biztalk-assemblies.md)