---
title: "Cómo usar contraseña filtra | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb429f8b-c301-45a3-8a4f-bbe6f2c566a3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ad35e2c3bec5b2ece69911b8de8c7fd13c9b790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-password-filters"></a>Cómo usar filtros de contraseña
La característica de sincronización de contraseñas de ENTSSO sincroniza contraseñas entre los sistemas Microsoft Windows Active Directory y otros ajenos a Windows. Sin embargo, muchos sistemas externos tiene requisitos de política de contraseñas diferentes de los de Active Directory. (Por ejemplo, es posible que un sistema IBM requiera que la contraseña se escriba en mayúsculas y tenga un límite de 8 caracteres.) Esto fuerza a ENTSSO a usar el “denominador común mínimo” entre los dos sistemas, lo que limita la seguridad de las contraseñas.  
  
 La característica de filtro de contraseña de ENTSSO aborda esta limitación. Un filtro de contraseñas es simplemente un adaptador de sincronización de contraseñas con otras propiedades definidas. Éstas (por ejemplo, longitud máximo o mínima, mayúsculas o minúsculas y restricciones de número de caracteres) sirven para filtrar las contraseñas de modo que cumplan los criterios requeridos en el sistema externo.  
  
 Tenga en cuenta que al crear un filtro de contraseña, el grupo de administrador especificado se usa de forma automática como la cuenta de administradores de SSO. Si cambia el grupo de administradores de SSO, deberá asegurarse de que el filtro de contraseñas también se actualiza con la nueva cuenta de administradores de SSO.  
  
> [!NOTE]
>  Igual que con todos los elementos del sistema ENTSSO, los filtros de contraseñas contienen información muy confidencial y deberían conocerlos el menor número de personas posible.  
  
### <a name="to-create-a-password-filter"></a>Para crear un filtro de contraseñas  
  
1.  En el **consola de administración de SSO**, haga clic en el **administración de contraseñas** nodo y, a continuación, haga clic en **Crear filtro**.  
  
     El **Asistente de filtro de contraseña** aparece.  
  
2.  Siga las instrucciones del asistente para crear el filtro de contraseñas.  
  
### <a name="to-assign-an-affiliate-application-to-a-password-filter"></a>Para asignar una aplicación afiliada a un filtro de contraseñas  
  
1.  Haga clic en el filtro apropiado y, a continuación, haga clic en **asignar**...  
  
2.  Seleccione la **aplicación afiliada**.