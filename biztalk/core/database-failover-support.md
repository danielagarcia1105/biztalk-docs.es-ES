---
title: Compatibilidad de conmutación por error de la base de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09347fdd-2929-4ed9-b0d8-698508663ecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bbc795191eb2c13ca35d55846719cebc20d61a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238636"
---
# <a name="database-failover-support"></a><span data-ttu-id="9b64c-102">Compatibilidad con la conmutación por error de la base de datos</span><span class="sxs-lookup"><span data-stu-id="9b64c-102">Database Failover Support</span></span>
<span data-ttu-id="9b64c-103">Puede pasar una instancia de la **PolicyFetchErrorHandler** delegado como un parámetro a los constructores sobrecargados de la **directiva** clase.</span><span class="sxs-lookup"><span data-stu-id="9b64c-103">You can pass an instance of the **PolicyFetchErrorHandler** delegate as a parameter to overloaded constructors of the **Policy** class.</span></span> <span data-ttu-id="9b64c-104">Cuando se produce un error al capturar los detalles de la directiva de la base de datos, se invoca la instancia del delegado.</span><span class="sxs-lookup"><span data-stu-id="9b64c-104">When an error occurs while fetching the policy details from the database, the delegate instance is invoked.</span></span> <span data-ttu-id="9b64c-105">También puede usar un bloque try-catch para capturar **capturar** y **RuleStoreCompatibilityException** las excepciones que se producen cuando el motor de reglas no se puede conectar al motor de reglas base de datos.</span><span class="sxs-lookup"><span data-stu-id="9b64c-105">You can also use a try-catch block to trap **RuleStoreConnectionException** and **RuleStoreCompatibilityException** exceptions that are raised when the rule engine fails to connect to the Rule Engine database.</span></span>  
  
 <span data-ttu-id="9b64c-106">Si no se pasa una instancia de la **PolicyFetchErrorHandler** delegado como un parámetro a la **directiva** constructor, o si utiliza la **CallRules** forma en un orquestación, a continuación, si un error se produce al capturar los detalles de la directiva de la base de datos, producirán los eventos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9b64c-106">If you do not pass an instance of the **PolicyFetchErrorHandler** delegate as a parameter to the **Policy** constructor, or if you use the **CallRules** shape in an orchestration, then if an error occurs while fetching the policy details from the database, the following events happen:</span></span>  
  
1.  <span data-ttu-id="9b64c-107">El motor de reglas utiliza los valores de la **PolicyFetchErrorHandlerAssembly** y **PolicyFetchErrorHandlerClass** entradas del registro bajo **HKEY_LOCAL_MACHINE\Software\Microsoft\ BusinessRules\3.0**.</span><span class="sxs-lookup"><span data-stu-id="9b64c-107">The rule engine uses the values of the **PolicyFetchErrorHandlerAssembly** and **PolicyFetchErrorHandlerClass** registry entries under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**.</span></span> <span data-ttu-id="9b64c-108">Los valores predeterminados de la **PolicyFetchErrorHandlerAssembly** y **PolicyFetchErrorHandlerClass** entradas del registro son **Microsoft.BizTalk.RuleEngineExtensions**y **Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9b64c-108">The default values for the **PolicyFetchErrorHandlerAssembly** and **PolicyFetchErrorHandlerClass** registry entries are **Microsoft.BizTalk.RuleEngineExtensions** and **Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper** respectively.</span></span>  
  
2.  <span data-ttu-id="9b64c-109">El **ExceptionHelper** la clase implementa la **IPolicyFetchErrorMaker** interfaz.</span><span class="sxs-lookup"><span data-stu-id="9b64c-109">The **ExceptionHelper** class implements the **IPolicyFetchErrorMaker** interface.</span></span>  
  
3.  <span data-ttu-id="9b64c-110">El motor de reglas, se invoca el **get_ErrorHandler** método en el **IPolicyFetchErrorMaker** de la interfaz para obtener un puntero al método de control de errores y lo invoca.</span><span class="sxs-lookup"><span data-stu-id="9b64c-110">The rule engine invokes the **get_ErrorHandler** method on the **IPolicyFetchErrorMaker** interface to get a pointer to the error-handling method and invokes it.</span></span>  
  
4.  <span data-ttu-id="9b64c-111">El método de control de errores predeterminado, se invoca el **SetDBFailure** método, que se define en el archivo BTSDBAccessor.dll.</span><span class="sxs-lookup"><span data-stu-id="9b64c-111">The default error-handling method invokes the **SetDBFailure** method, which is defined in BTSDBAccessor.dll.</span></span>  
  
5.  <span data-ttu-id="9b64c-112">El **SetDBFailure** método hace que el servicio de BizTalk cerrar.</span><span class="sxs-lookup"><span data-stu-id="9b64c-112">The **SetDBFailure** method causes the BizTalk service to shut down.</span></span> <span data-ttu-id="9b64c-113">El servicio de BizTalk se reinicia transcurrido un minuto y se cierra si las bases de datos siguen sin estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="9b64c-113">The BizTalk service restarts in one minute and shuts down if the databases are still not available.</span></span> <span data-ttu-id="9b64c-114">Este ciclo se repite hasta que las bases de datos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9b64c-114">This cycle repeats until the databases are available.</span></span>