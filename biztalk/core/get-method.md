---
title: "Get (método) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Get method
ms.assetid: 0e621077-f0ef-495c-ba6b-0c6154f48113
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d56b060cc261f707a4aa7b0d6a496a62707c4dca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-method"></a>Método Get
Usar para recuperar propiedades basándose en los parámetros de clave de entrada (clave1, clave2... claven). El parámetro de salida es una estructura que contiene las propiedades del registro que coincide con los parámetros de clave. Si la interfaz de componente tiene solo una instancia (es decir, no hay ninguna clave), la función Get no contiene ningún parámetro de clave. Consulte también [método Find](../core/find-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Get (key1, key2, ... keyn, properties)  
Get (key1, key2, ... keyn, getHistoryItems, properties)  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Description|  
|---------------|-----------------|  
|`key`|Conjunto de parámetros que debe existir en la base de datos del servidor; de lo contrario, se produce un error. Estas claves corresponden al conjunto de Get Keys definido para la interfaz de componentes concreta.|  
|`properties`|Contiene una estructura completa de las propiedades de la interfaz de componentes, que se devuelve al completarse la llamada.|  
|`getHistoryItems`|Valor booleano. Si las propiedades de la interfaz de componentes contienen elementos con fecha de vigencia por debajo del nivel 0 (es decir, un campo de claves con el nombre EFFDT), es obligatorio el parámetro adicional `getHistoryItems`.<br /><br /> Si el valor es:<br /><br /> -True: todos los elementos con fecha de vigencia se devuelven como una secuencia (que puede estar insertada en cualquier nivel). Entre ellos se incluyen todos los elementos con fecha de vigencia pasada, el elemento con fecha de vigencia actual y todos los elementos con fecha de vigencia futura<br />-False, se devuelven solo la actual y todos los elementos con fecha de vigencia futuros. Si se van a realizar otras llamadas para actualizar en la misma instancia, el parámetro `getHistoryItems` debe establecerse en False.|  
  
### <a name="remarks"></a>Comentarios  
 Si las propiedades de la interfaz de componentes contienen elementos con fecha de vigencia por debajo del nivel 0 (es decir, un campo de clave con el nombre EFFDT), es obligatorio el parámetro adicional `getHistoryItems`. Este parámetro es de tipo booleano. Si se establece en True, todos los elementos con fecha de vigencia se devuelven como secuencia (que puede estar insertada en cualquier nivel). Entre ellos se incluyen todos los elementos con fecha de vigencia pasada, el elemento con fecha de vigencia actual y todos los elementos con fecha de vigencia futura. Si el parámetro `getHistoryItems` se establece en False, solamente se devolverán el elemento con fecha de vigencia actual y todos los futuros. Si deben realizarse otras llamadas para actualizar en la misma instancia, el parámetro `getHistoryItems` debe establecerse en False. Vea también [método UpdateEx](../core/updateex-method.md).  
  
 Si la interfaz de componentes no tiene clave, como sucede si solo puede existir una instancia, el método `Get()` tiene el formato:  
  
```  
Get(properties)  
```  
  
 Para obtener más información sobre los elementos con fecha de vigencia, vea la documentación de PeopleSoft Enterprise.  
  
> [!NOTE]
>  Se proporciona el método `Get()` del Adaptador de BizTalk para PeopleSoft Enterprise si se habilita la función `Get` de PeopleSoft en la interfaz de componentes.  
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md)