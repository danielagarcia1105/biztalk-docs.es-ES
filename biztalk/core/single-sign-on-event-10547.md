---
title: 'Inicio de sesión único: Evento 10547 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be25cdc9-d6c1-488d-9ead-877a2454c3d1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6162461b1eb04993ca681049fe1fbb797ca014
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270724"
---
# <a name="single-sign-on-event-10547"></a>Inicio de sesión único: Evento 10547
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10547|  
|Origen del evento|ENTSSO|  
|Componente|CO|  
|Nombre simbólico|SSO_WARN_UPDATE_FAILED|  
|Texto del mensaje|No se pudieron actualizar las credenciales en la base de datos de SSO durante el recifrado.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no fue posible actualizar las credenciales con el resultado del nuevo cifrado. Cuando se cambia el secreto principal, ya sea al generar un secreto nuevo o al restaurar un secreto anterior, se vuelve a realizar el cifrado en la base de datos de SSO para descifrar todos los servicios cifrados con el secreto anterior y volver a cifrarlos con el secreto nuevo. Este evento puede producirse si las credenciales se eliminaron debido a que estaban en proceso de ser cifradas nuevamente.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Espere a que se produzca otro recifrado después de un breve retardo, si esto no se produce automáticamente, reinicie el servicio SSO que desencadenará un nuevo recifrado si es necesario.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Entendiendo SSO](../core/understanding-sso.md)