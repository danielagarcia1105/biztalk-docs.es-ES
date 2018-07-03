---
title: Cómo modificar las opciones de implementación de un ensamblado .NET, un componente COM, un archivo o un artefacto de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [.NET assemblies], deploying
- deploying, virtual directories
- managing [applications], deploying
- managing [applications], modifying
- definition files [BAM], modifying
- modifying, artifacts
- deploying, artifacts
- managing [certificates], deploying
- deploying, .NET assemblies
- COM components, deploying
- definition files [BAM], deploying
- virtual directories, deploying
- deploying, certificates
- modifying, deployment options
- virtual directories, modifying
- deploying, COM components
ms.assetid: 4955d420-d9ff-4d5a-82f4-fb16477a828c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 641e955a5eed0bb18df90b170daa6b87feba0876
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992013"
---
# <a name="how-to-modify-the-deployment-options-of-a-net-assembly-com-component-file-or-bam-artifact"></a>Cómo modificar las opciones de implementación de un ensamblado .NET, un componente COM, un archivo o un artefacto de BAM
En este tema se describe cómo usar la consola de administración de BizTalk Server para modificar las opciones de implementación de los artefactos de recursos siguientes:  
  
- Ensamblados .NET  
  
- Componentes COM  
  
- Archivos ad hoc  
  
- Artefactos de BAM  
  
  Puede que desee modificar las propiedades de implementación para cambiar la ubicación de destino en que se copiará el artefacto cuando la aplicación se instale en el equipo local. Si no proporciona una ruta, el archivo no se copiará en el equipo local durante la instalación.  
  
  Además, puede que desee modificar las opciones siguientes para un ensamblado .NET:  
  
- **Agregar a la caché global de ensamblados de agregar recursos (gacutil).** al activar esta opción, el ensamblado se agrega a la caché de ensamblados global (GAC) en el equipo local cuando el ensamblado se agrega a la aplicación. Además, si actualiza posteriormente el ensamblado (haga clic en él y haga clic en **actualizar**), el ensamblado se agrega a la GAC. Al desactivar la casilla de verificación de esta opción, el ensamblado no se quita de la GAC si actualmente existe en dicho lugar.  
  
- **Agregar a la caché global de ensamblados en la importación de archivo MSI (gacutil).** al seleccionar esta opción, si se ha exportado la aplicación a un archivo .msi y el archivo .msi se ha importado en un grupo de BizTalk, el ensamblado se instala en la GAC del equipo local como parte del proceso de importación.  
  
- **Agregar a la caché global de ensamblados en la instalación de archivos MSI (gacutil).** Al seleccionar esta opción, si se ha exportado la aplicación a un archivo .msi y se ha instalado la aplicación en un equipo desde el archivo .msi, el ensamblado se instala en la GAC del equipo local como parte del proceso de instalación.  
  
- **Hacer visibles para los componentes COM (regasm).** al seleccionar esta opción, si la aplicación se ha exportado a un archivo .msi y se ha instalado en un equipo desde el archivo .msi, se agrega un ensamblado COM administrado al Registro de Windows en el equipo local como parte del proceso de instalación. Si especifica esta opción, también debe especificar una ubicación para el archivo en Destino.  
  
- **Registrar componentes con servicio (regsvcs).** al seleccionar esta opción, si la aplicación se ha exportado a un archivo .msi y se ha instalado en un equipo desde el archivo .msi, se agrega un ensamblado COM+ administrado al Registro de Windows en el equipo local como parte del proceso de instalación. Si especifica esta opción, también debe especificar una ubicación para el archivo en Destino.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Además, si selecciona una opción que agrega inmediatamente el ensamblado a la GAC, la cuenta debe pertenecer también al grupo de administradores local. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-modify-the-deployment-properties-of-a-resource-artifact"></a>Para modificar las propiedades de implementación de un artefacto de recurso  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], el grupo de BizTalk que contiene el artefacto cuyas opciones de implementación desea modificar y, a continuación, la aplicación que contiene el artefacto.  
  
3. Haga clic en el **recursos** carpeta, haga clic en el artefacto y, a continuación, haga clic en **modificar**.  
  
4. En el **opciones** pestaña, modifique las opciones de implementación según sea necesario y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de ensamblados .NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)