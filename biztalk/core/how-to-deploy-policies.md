---
title: "Cómo implementar directivas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c4ab85a-5a6a-4153-90dc-52e099c0a62c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c3b07b0a8cebdd3322b49732ef4f32c04cbfede
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-policies"></a>Cómo implementar directivas
Puede implementar directivas mediante programación utilizando la [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) clase en el **Microsoft.RuleEngine.RuleEngineExtensions** espacio de nombres. El código de ejemplo siguiente muestra cómo utilizar el [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) clase para implementar una directiva denominada **LoanProcessing**:  
  
```  
string policyName = “LoanProcessing”;  
int majorRev = Convert.ToInt16(args[1]);  
int minorRev = Convert.ToInt16(args[2]);  
RuleSetInfo rsi = new RuleSetInfo(policyName,majorRev,minorRev);  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
dd.Deploy(rsi);  
```  
  
> [!NOTE]
>  Los constructores sobrecargados de la [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) clase toman los nombres de la base de datos de almacén de reglas como parámetro. Esto permite implementar directivas en una base de datos que el entorno de BizTalk Server no está configurado para utilizar.  
  
## <a name="using-the-getdeploymentdriver-method"></a>Usar el método GetDeploymentDriver  
 Si va a implementar las directivas en la base de datos que su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno está configurado para usar, no tendrá que crear el **RuleSetDeploymentDriver** objeto en el código. En su lugar, puede solicitar el motor de reglas para crear un **RuleSetDeploymentDriver** objeto invocando la **GetDeploymentDriver** método de la **configuración** clase en el **System.RuleEngine** espacio de nombres. El código de ejemplo siguiente muestra cómo invocar el **GetDeploymentDriver** método:  
  
```  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.RuleEngine.Configuration.GetDeploymentDriver();  
```  
  
 El **GetDeploymentDriver** método recupera los valores de la **DeploymentDriverAssembly** y **DeploymentDriverClass** claves del registro bajo **HKEY_ LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**y crea una instancia de **DeploymentDriverClass**. La siguiente tabla muestra los valores predeterminados de estas dos claves de Registro.  
  
|Clave del Registro|Valor|  
|------------------|-----------|  
|DeploymentDriverAssembly|Microsoft.BizTalk.RuleEngineExtensions|  
|DeploymentDriverClass|Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver|  
  
 El **RuleSetDeploymentDriver** la clase implementa la **IRuleSetDeploymentDriver** interfaz. Puede desarrollar su propio controlador de implementación de directiva mediante la creación de una clase que implementa el **IRuleSetDeploymentDriver** interfaz y cambie los valores de las claves del registro se ha descrito anteriormente como corresponda.