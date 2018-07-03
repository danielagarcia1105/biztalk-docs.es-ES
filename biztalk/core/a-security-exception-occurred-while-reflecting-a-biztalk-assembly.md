---
title: Se produjo una excepción de seguridad al reflejar el ensamblado de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 301b85c7-8e67-482e-8666-67a91ca5c73d
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d07b1e5788ae696e94a3bbe326f2cfe79d1b76f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979933"
---
# <a name="a-security-exception-occurred-while-reflecting-a-biztalk-assembly"></a>Excepción de seguridad al reflejar el ensamblado de BizTalk
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                 |
| Versión del producto |                                                                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                             |
|    Identificador del evento     |                                                                                                                                                                         0                                                                                                                                                                          |
|  Origen del evento   |                                                                                                                                                                         0                                                                                                                                                                          |
|    Componente    |                                                                                                                                                                         0                                                                                                                                                                          |
|  Nombre simbólico  |                                                                                                                                                                         0                                                                                                                                                                          |
|  Texto del mensaje   | Se produjo una excepción de seguridad al reflejar el ensamblado de BizTalk "{0}". El problema surge si el ensamblado está ubicado en una carpeta de red compartida. Para corregir este problema, pruebe uno de los siguientes: 1. Copie el ensamblado y sus dependencias en el equipo local. 2. Ajuste la directiva de seguridad en tiempo de ejecución de la configuración .NET para permitir el acceso. |
  
## <a name="explanation"></a>Explicación  
 Este error se producirá al intentar publicar un ensamblado de BizTalk que está en una red compartida sin la directiva .NET correcta.  
  
## <a name="user-action"></a>Acción del usuario  
 Además de seguir los pasos específicos indicados en el mensaje de error, copie el ensamblado localmente. O bien, edite la directiva para conceder total confianza a la intranet local.  
  
 **Uso de la herramienta Directiva de seguridad de acceso a código (Caspol.exe)**  
  
 Puede conceder confianza a una carpeta del equipo local en el nivel de usuario con permisos de usuario normales. Para conceder confianza a una ubicación de red, debe disponer de privilegios de administrador y cambiar la directiva de seguridad en el nivel de equipo. El nivel de directiva de equipo actúa independientemente del nivel de directiva de usuario, y el nivel de directiva de equipo no concede total confianza a la zona de intranet aunque la directiva de usuario lo haga. Los niveles de directiva deben coincidir.  
  
 **Para conceder total confianza a una carpeta local**  
  
-   Escriba el comando siguiente en el símbolo del sistema de Visual Studio:  
  
```  
caspol -u -ag All_Code -url   
C:\<FolderName>\<FolderName>\* FullTrust -n "<Name>" -d  
"<Description>"  
```  
  
 **Para conceder plena confianza a una carpeta de red**  
  
-   Escriba el comando siguiente en el símbolo del sistema de Visual Studio:  
  
```  
caspol -m -ag LocalIntranet_Zone -url   
\\<ServerName>\<FolderName>\* FullTrust -n "<Name>" -d   
"<Description>"  
```