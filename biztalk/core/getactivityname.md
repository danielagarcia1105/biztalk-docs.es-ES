---
title: GetActivityName | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 479552fa-1535-4f3d-90ff-4615f14c88b1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55e8f35746f5f4ed1bbbe10a4d45300895340869
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getactivityname"></a>GetActivityName
Inserta el nombre de la actividad en curso en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wf:Operation Name="GetActivityName"/>  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el nombre de la actividad en curso.  
  
## <a name="remarks"></a>Comentarios  
 Windows Workflow Foundation realiza su trabajo como una serie de actividades configurada por el programador. Cada una de estas actividades tiene asignada un nombre único en el flujo de trabajo. Puede interceptar datos para una actividad específica mediante el filtrado, basándose en su nombre único.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo contiene una expresión de filtro de eventos configurada para buscar una actividad específica, FoodAndDrinksPolicy, en un flujo de trabajo cerrado. Para ello, se usa una combinación de operaciones, incluidas `GetActivityName`, `GetActivityEvent` y operaciones lógicas.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 Este patrón de filtro es habitual con los archivos de configuración del interceptor de Windows Workflow Foundation.  
  
> [!NOTE]
>  Los argumentos no requieren comillas dobles a menos que intente hacer coincidir, de forma explícita, una cadena que contiene comillas dobles.