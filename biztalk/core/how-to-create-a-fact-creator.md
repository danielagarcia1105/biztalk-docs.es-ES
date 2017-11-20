---
title: "Cómo crear un creador de hechos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GetFactTypes method
- CreateFacts method
- IFactCreator interface
- Business Rules Framework, code samples
- Business Rules Framework, fact creator
- Business Rules Framework, programming
ms.assetid: 0589be8e-34d6-4e55-b678-c1f8436d1f61
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cba9c46a147d912ae22644a30ef65c0b0213202
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-fact-creator"></a><span data-ttu-id="e5a00-102">Cómo crear creadores de hechos</span><span class="sxs-lookup"><span data-stu-id="e5a00-102">How to Create a Fact Creator</span></span>
<span data-ttu-id="e5a00-103">Puede escribir un creador de hechos para crear instancias de hechos.</span><span class="sxs-lookup"><span data-stu-id="e5a00-103">You can write a fact creator to create instances of your facts.</span></span> <span data-ttu-id="e5a00-104">El creador de hechos debe implementar **IFactCreator** y su **CreateFacts** método y **GetFactTypes** método.</span><span class="sxs-lookup"><span data-stu-id="e5a00-104">Your fact creator must implement **IFactCreator** and its **CreateFacts** method and **GetFactTypes** method.</span></span> <span data-ttu-id="e5a00-105">Una vez que haya creado el DLL del creador de hechos, puede desplazarse hasta ella desde el comprobador de directivas.</span><span class="sxs-lookup"><span data-stu-id="e5a00-105">After you have created your fact creator dll, you can browse to it from within the policy tester.</span></span> <span data-ttu-id="e5a00-106">A continuación se muestra un ejemplo de la implementación de un creador de hechos.</span><span class="sxs-lookup"><span data-stu-id="e5a00-106">The following is an example of a fact creator implementation.</span></span>  
  
```  
public class MyFactCreator : IFactCreator  
{  
   private object[] myFacts;  
   public MyFactCreator()  
   {  
   }  
   public object[] CreateFacts ( RuleSetInfo rulesetInfo )  
   {  
      myFacts = new object[1];  
      myFacts.SetValue(new MySampleBusinessObject(),0);  
      return myFacts;  
   }  
   public Type[] GetFactTypes (RuleSetInfo rulesetInfo)  
   {  
      return null;  
   }  
}  
```