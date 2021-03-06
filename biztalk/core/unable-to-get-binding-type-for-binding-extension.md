---
title: No se puede obtener el tipo de enlace para la extensión de enlace | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7cfc81-7439-48f9-8cac-42b2419ecd9d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdf0e0fd1ebf88c9231d70e9102d76fa67157cb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006237"
---
# <a name="unable-to-get-binding-type-for-binding-extension"></a>No se puede obtener el tipo de enlace para la extensión de enlace
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                        |
| Versión del producto |                                                                                    [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                    |
|    Identificador del evento     |                                                                                                                0                                                                                                                 |
|  Origen del evento   |                                                                                                                0                                                                                                                 |
|    Componente    |                                                                                                                0                                                                                                                 |
|  Nombre simbólico  |                                                                                                                0                                                                                                                 |
|  Texto del mensaje   | No se puede obtener el tipo de enlace para la extensión de enlace "{0}". Si machine.config se actualizó mientras estaba abierta la aplicación, reinicie la aplicación para que se apliquen los cambios. Compruebe que la extensión de enlace está registrada en machine.config. |

## <a name="explanation"></a>Explicación  
 Una extensión de enlace personalizado para un transporte WCF-Custom o WCF-CustomIsolated no se configuró correctamente.  

## <a name="user-action"></a>Acción del usuario  
 Par resolver este error, realice una de las acciones siguientes:  

- Asegúrese del **archivo.config** en **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config** tiene la \< **bindingExtensions** \> elemento configurado correctamente.  

- En el Explorador de Windows, vaya a **%WinDir%\Assembly**y asegúrese de que los ensamblados que implementan la extensión de enlace personalizada están instalados correctamente.  

- Para el adaptador de WCF-Custom, en la consola de administración de BizTalk, reinicie la instancia de host que ejecuta el transporte WCF.  

- Para el adaptador de WCF-CustomIsolated, en la consola de administración de IIS, reinicie el grupo de aplicaciones que hospeda el transporte WCF.  

- Abra y cierre la consola de administración de BizTalk si estaba abierta.  

  Para obtener más información, vea el recurso siguiente:  

- [Cómo habilitar los puntos de extensibilidad de WCF con adaptadores de WCF](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)
