---
title: "Cómo crear scripts de implementación de directivas empresariales y de importación y exportación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, policies
- business rules, deploying
- policies, deploying
- business rules, exporting
- RuleSetDeploymentDriver
- business rules, importing
- Business Rules Framework, policies
- Business Rules Framework, business rules
- Business Rules Framework, code samples
- deploying, business rules
- Business Rules Framework, programming
ms.assetid: 333d37dc-e0ee-460c-922d-70eedf7b7ccb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fda67a54c63c8d1dd092e615b2057f00ad41bba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-script-import-export-and-deployment-of-business-policies"></a><span data-ttu-id="c7bb4-102">Cómo crear scripts de importación y exportación y la implementación de directivas empresariales</span><span class="sxs-lookup"><span data-stu-id="c7bb4-102">How to Script Import-Export and Deployment of Business Policies</span></span>
<span data-ttu-id="c7bb4-103">Esta sección describe cómo mediante programación importación/exportación e implementar directivas mediante **RuleSetDeploymentDriver**.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-103">This section describes how to programmatically import/export and deploy policies using **RuleSetDeploymentDriver**.</span></span>  
  
 <span data-ttu-id="c7bb4-104">En el ejemplo siguiente se muestra cómo exportar una directiva a un archivo.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-104">The following example shows how to export a policy to a file.</span></span>  
  
```  
using System;  
using Microsoft.RuleEngine;  
using Microsoft.BizTalk.RuleEngineExtensions;  
namespace SimpleExport  
{  
   class ExportPolicy  
   {  
      [STAThread]  
      static void Main(string[] args)  
      {  
         if (args.Length != 3)  
            Console.WriteLine("Format: PolicyName MajorVersion MinorVersion");  
         else  
         {  
            string policyName = args[0];  
            int majorRev = Convert.ToInt16(args[1]);  
            int minorRev = Convert.ToInt16(args[2]);  
            RuleSetInfo rsi = new RuleSetInfo(policyName,majorRev,minorRev);  
            Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
            dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
                        string fileName = (rsi.Name + "-" + rsi.MajorRevision + "." + rsi.MinorRevision + ".xml");  
            dd.ExportRuleSetToFileRuleStore(rsi,fileName);  
         }  
      }  
   }  
}  
```  
  
 <span data-ttu-id="c7bb4-105">En el ejemplo siguiente se muestra cómo se puede importar e implementar una directiva desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-105">The following example shows how you can import and deploy a policy from a file.</span></span>  
  
```  
using System;  
using Microsoft.RuleEngine;  
using Microsoft.BizTalk.RuleEngineExtensions;  
namespace SimpleImport  
{  
   class ImportPolicy  
   {  
      [STAThread]  
      static void Main(string[] args)  
      {  
         String filename = args[0];  
         Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
         dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
         SqlRuleStore sqlRuleStore = (SqlRuleStore) dd.GetRuleStore();  
         FileRuleStore fileRuleStore = new FileRuleStore(filename);  
         RuleSetInfoCollection rsic = fileRuleStore.GetRuleSets(RuleStore.Filter.All);  
         foreach (RuleSetInfo rsi in rsic)  
         {  
            RuleSet ruleSet = fileRuleStore.GetRuleSet(rsi);  
            bool publishRuleSets = true;  
            sqlRuleStore.Add(ruleSet,publishRuleSets);  
            dd.Deploy(rsi);  
         }  
      }  
   }  
}    
```  
  
> [!NOTE]
>  <span data-ttu-id="c7bb4-106">En el código se asume que no existen dependencias de vocabularios; si la directiva utiliza vocabularios deben importarse en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-106">The code assumes no dependencies on vocabularies; if the policy uses vocabularies they must be imported first.</span></span>