---
title: 'De sesión único: Evento 10512 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edf0512-112d-40b8-9e29-7dd67f999b6d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54ba5a340a1a7590dae72016a3e747726ea68125
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980965"
---
# <a name="single-sign-on-event-10512"></a>De sesión único: Evento 10512
## <a name="details"></a>Detalles  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10512                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N\D                             |
|  Nombre simbólico  |                   SSO_ERROR_LOADLIBRARY                    |
|  Texto del mensaje   |      No se pudo cargar %1%r<br /><br /> Código de error: %2.       |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que la Biblioteca de vínculos dinámicos (DLL) no se pudo cargar en el proceso del servidor de SSO. La falta de la DLL en el directorio de instalación de SSO (normalmente, C:\Archivos de programa\Archivos comunes\Inicio de sesión único empresarial) puede indicar que el programa de instalación no se completó correctamente o que la DLL se eliminó después de que éste se completó. Si la DLL está presente, el servicio SSO podría tener problemas con la resolución de la ruta de acceso correcta a ella. Además, la DLL podría estar dañada.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  

- Si se sospecha que puede existir un error más grave de instalación, tal vez sea necesario desinstalar el producto y volver a instalarlo.  

- Si la única DLL falta o está dañada, intente reemplazarla y, seguidamente, reinicie el servicio.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)
