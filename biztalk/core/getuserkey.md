---
title: Getuserkey (operación) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9353a7f0-9bbd-4cfa-92e6-ed2b86e3a88e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0701ff1df912cc113205bad573b6cebc0f02a13a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246124"
---
# <a name="getuserkey"></a>GetUserKey (operación)
Inserta la clave usuario actual en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wf:Operation Name="GetUserKey" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene la clave del usuario actual.  
  
## <a name="remarks"></a>Comentarios  
 Esta operación sólo es válida en las puntos de seguimiento del usuario.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo contiene un filtro de evento que se evaluará como `true` cuando la clave del usuario es igual a "DocumentUrl".  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```