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
# <a name="how-to-deploy-policies"></a><span data-ttu-id="6a6df-102">Cómo implementar directivas</span><span class="sxs-lookup"><span data-stu-id="6a6df-102">How to Deploy Policies</span></span>
<span data-ttu-id="6a6df-103">Puede implementar directivas mediante programación utilizando la [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) clase en el **Microsoft.RuleEngine.RuleEngineExtensions** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6a6df-103">You can deploy policies programmatically by using the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class in the **Microsoft.RuleEngine.RuleEngineExtensions** namespace.</span></span> <span data-ttu-id="6a6df-104">El código de ejemplo siguiente muestra cómo utilizar el [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) clase para implementar una directiva denominada **LoanProcessing**:</span><span class="sxs-lookup"><span data-stu-id="6a6df-104">The following sample code demonstrates how to use the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class to deploy a policy named **LoanProcessing**:</span></span>  
  
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
>  <span data-ttu-id="6a6df-105">Los constructores sobrecargados de la [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) clase toman los nombres de la base de datos de almacén de reglas como parámetro.</span><span class="sxs-lookup"><span data-stu-id="6a6df-105">The overloaded constructors of the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class take the names of the rule store database as a parameter.</span></span> <span data-ttu-id="6a6df-106">Esto permite implementar directivas en una base de datos que el entorno de BizTalk Server no está configurado para utilizar.</span><span class="sxs-lookup"><span data-stu-id="6a6df-106">This allows you to deploy policies to a database that your BizTalk Server environment is not configured to use.</span></span>  
  
## <a name="using-the-getdeploymentdriver-method"></a><span data-ttu-id="6a6df-107">Usar el método GetDeploymentDriver</span><span class="sxs-lookup"><span data-stu-id="6a6df-107">Using the GetDeploymentDriver Method</span></span>  
 <span data-ttu-id="6a6df-108">Si va a implementar las directivas en la base de datos que su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno está configurado para usar, no tendrá que crear el **RuleSetDeploymentDriver** objeto en el código.</span><span class="sxs-lookup"><span data-stu-id="6a6df-108">If you are deploying policies to the database that your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is configured to use, you do not have to create the **RuleSetDeploymentDriver** object in the code.</span></span> <span data-ttu-id="6a6df-109">En su lugar, puede solicitar el motor de reglas para crear un **RuleSetDeploymentDriver** objeto invocando la **GetDeploymentDriver** método de la **configuración** clase en el **System.RuleEngine** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6a6df-109">Instead, you can request the rule engine to create a **RuleSetDeploymentDriver** object for you by invoking the **GetDeploymentDriver** method of the **Configuration** class in the **System.RuleEngine** namespace.</span></span> <span data-ttu-id="6a6df-110">El código de ejemplo siguiente muestra cómo invocar el **GetDeploymentDriver** método:</span><span class="sxs-lookup"><span data-stu-id="6a6df-110">The following sample code demonstrates how to invoke the **GetDeploymentDriver** method:</span></span>  
  
```  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.RuleEngine.Configuration.GetDeploymentDriver();  
```  
  
 <span data-ttu-id="6a6df-111">El **GetDeploymentDriver** método recupera los valores de la **DeploymentDriverAssembly** y **DeploymentDriverClass** claves del registro bajo **HKEY_ LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**y crea una instancia de **DeploymentDriverClass**.</span><span class="sxs-lookup"><span data-stu-id="6a6df-111">The **GetDeploymentDriver** method retrieves the values of the **DeploymentDriverAssembly** and **DeploymentDriverClass** registry keys under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, and creates an instance of **DeploymentDriverClass**.</span></span> <span data-ttu-id="6a6df-112">La siguiente tabla muestra los valores predeterminados de estas dos claves de Registro.</span><span class="sxs-lookup"><span data-stu-id="6a6df-112">The following table shows the default values of these two registry keys.</span></span>  
  
|<span data-ttu-id="6a6df-113">Clave del Registro</span><span class="sxs-lookup"><span data-stu-id="6a6df-113">Registry key</span></span>|<span data-ttu-id="6a6df-114">Valor</span><span class="sxs-lookup"><span data-stu-id="6a6df-114">Value</span></span>|  
|------------------|-----------|  
|<span data-ttu-id="6a6df-115">DeploymentDriverAssembly</span><span class="sxs-lookup"><span data-stu-id="6a6df-115">DeploymentDriverAssembly</span></span>|<span data-ttu-id="6a6df-116">Microsoft.BizTalk.RuleEngineExtensions</span><span class="sxs-lookup"><span data-stu-id="6a6df-116">Microsoft.BizTalk.RuleEngineExtensions</span></span>|  
|<span data-ttu-id="6a6df-117">DeploymentDriverClass</span><span class="sxs-lookup"><span data-stu-id="6a6df-117">DeploymentDriverClass</span></span>|<span data-ttu-id="6a6df-118">Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver</span><span class="sxs-lookup"><span data-stu-id="6a6df-118">Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver</span></span>|  
  
 <span data-ttu-id="6a6df-119">El **RuleSetDeploymentDriver** la clase implementa la **IRuleSetDeploymentDriver** interfaz.</span><span class="sxs-lookup"><span data-stu-id="6a6df-119">The **RuleSetDeploymentDriver** class implements the **IRuleSetDeploymentDriver** interface.</span></span> <span data-ttu-id="6a6df-120">Puede desarrollar su propio controlador de implementación de directiva mediante la creación de una clase que implementa el **IRuleSetDeploymentDriver** interfaz y cambie los valores de las claves del registro se ha descrito anteriormente como corresponda.</span><span class="sxs-lookup"><span data-stu-id="6a6df-120">You can develop your own policy deployment driver by creating a class that implements the **IRuleSetDeploymentDriver** interface and change the values for the registry keys described above as appropriate.</span></span>