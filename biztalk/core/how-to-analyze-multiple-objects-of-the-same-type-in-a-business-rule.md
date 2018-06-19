---
title: Cómo analizar varios objetos del mismo tipo en una regla de negocios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, multiple types
- Business Rules Framework, programming
ms.assetid: ff9790c1-13b0-4eee-8cac-d4f25ef5f0b7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a1e4d2fb01513b1d4d314264ab74b84d3a0223a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248436"
---
# <a name="how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule"></a>Cómo analizar varios objetos del mismo tipo en una regla de negocios
En muchos escenarios, la regla empresarial se escribe con respecto a un tipo y se espera que cada instancia del tipo que se impone en el motor se analice independientemente y la regla actúe sobre ella. Sin embargo, en algunos escenarios, será conveniente analizar varias instancias de un tipo determinado de forma simultánea en una regla.  
  
 Tomemos, por ejemplo, una regla que use instancias de la **FamilyMember** clase.  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember.Role == Son  
AND FamilyMember.Surname == FamilyMember.Surname  
THEN FamilyMember.AddChild(FamilyMember)  
```  
  
 La regla identifica una **FamilyMember** instancia que es un **padre** y otra instancia que es un **hijo**. Si las instancias están relacionadas por el apellido, el **hijo** instancia se agrega a una colección de elementos secundarios en la instancia del padre. Si cada **FamilyMember** instancia se analizara independientemente de la regla, la regla nunca se activaría porque en este escenario, el **FamilyMember** sólo tiene una función:**padre** o **hijo**.  
  
 Por lo tanto, debe indicar al motor que se deben analizar varias instancias juntas en la regla y necesita una manera de diferenciar la identidad de cada instancia en la regla. El **Id. de instancia** propiedad se utiliza para proporcionar esta funcionalidad. Este campo está disponible en la ventana de propiedades cuando se selecciona un hecho en el Explorador de hechos. Debe cambiar el valor del campo antes de arrastrar un hecho o un miembro a la regla.  
  
 Mediante el **Id. de instancia** propiedad, se regenerará la regla. Para los argumentos de regla que utilicen el **hijo** instancia de **FamilyMember**, **Id. de instancia** campo se cambia el valor predeterminado de 0 a 1. Cuando se cambia el identificador de instancia entre 0 y el hecho o miembro se arrastra en el editor de reglas, el valor de Id. de instancia se mostrará en la regla después de la clase.  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember(1).Role== Son  
AND FamilyMember.Surname == FamilyMember(1).Surname  
THEN FamilyMember.AddChild(FamilyMember(1))  
```  
  
 Ahora, suponga que un **padre** instancia y un **hijo** instancia se imponen en el motor. El motor evaluará la regla con respecto a las distintas combinaciones de las instancias. Suponiendo que la **padre** y **hijo** instancia tengan el mismo apellido, el **hijo** instancia se agregarán a la **padre** instancia como diseñado.  
  
> [!NOTE]
>  El **Id. de instancia** solo se usa en el contexto de una evaluación determinado de reglas. No está fijada a la instancia de un objeto en toda la ejecución de la directiva y no está relacionada con el orden en que se imponen los objetos. Cada instancia del objeto se evaluará en todos los argumentos de la regla para ese tipo.