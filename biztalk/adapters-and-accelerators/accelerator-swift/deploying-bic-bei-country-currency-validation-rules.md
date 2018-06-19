---
title: Implementar reglas de validación de BIC BEI país divisa | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e96d416-d5eb-4597-a691-c7dbee33c7d6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57bdaa8f2a13b650019fa02b096ca05971389570
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964586"
---
# <a name="deploying-bicbeicountrycurrency-validation-rules"></a><span data-ttu-id="40982-102">Implementar reglas de validación de BIC/BEI/país/moneda</span><span class="sxs-lookup"><span data-stu-id="40982-102">Deploying BIC/BEI/Country/Currency Validation Rules</span></span>
<span data-ttu-id="40982-103">**Para implementar las reglas de validación de BIC/BEI/país/moneda:**</span><span class="sxs-lookup"><span data-stu-id="40982-103">**To deploy the BIC/BEI/Country/Currency Validation rules:**</span></span>  
  
1.  <span data-ttu-id="40982-104">El siguiente conjunto de directivas, % program files%\Microsoft Acelerador de BizTalk para directivas de Messages\Base de SWIFT\SDK\MX, que son genérico y no específica de los mensajes, necesitan que se publican y se implementa por separado utilizando al Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="40982-104">The following set of policies, %program files%\Microsoft BizTalk Accelerator for SWIFT\SDK\MX Messages\Base Policies, which are generic and not message-specific, need to be published and deployed separately using the Business Rule Engine Deployment Wizard.</span></span>  
  
    -   <span data-ttu-id="40982-105">MX_BIC_Master_Policy.Xml</span><span class="sxs-lookup"><span data-stu-id="40982-105">MX_BIC_Master_Policy.xml</span></span>  
  
    -   <span data-ttu-id="40982-106">MX_BIC_Validation_Policy.Xml</span><span class="sxs-lookup"><span data-stu-id="40982-106">MX_BIC_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="40982-107">MX_BEI_Validation_Policy.Xml</span><span class="sxs-lookup"><span data-stu-id="40982-107">MX_BEI_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="40982-108">MX_DBConnection_Master_Policy.Xml</span><span class="sxs-lookup"><span data-stu-id="40982-108">MX_DBConnection_Master_Policy.xml</span></span>  
  
    -   <span data-ttu-id="40982-109">MX_BICPlusIBAN_Validation_Policy.Xml</span><span class="sxs-lookup"><span data-stu-id="40982-109">MX_BICPlusIBAN_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="40982-110">MX_SEPA_Validation_Policy.Xml</span><span class="sxs-lookup"><span data-stu-id="40982-110">MX_SEPA_Validation_Policy.xml</span></span>  
  
2.  <span data-ttu-id="40982-111">Antes de implementar estas directivas, MX_DBConnection_Master_Policy.xml y MX_BIC_Master_Policy.xml deben tener el nombre del servidor de base de datos y el nombre de la base de datos donde se han almacenado los valores de país/moneda.</span><span class="sxs-lookup"><span data-stu-id="40982-111">Before deploying these policies, MX_DBConnection_Master_Policy.xml and MX_BIC_Master_Policy.xml should have the database server name and database name where the Country/Currency values have been stored.</span></span>  
  
3.  <span data-ttu-id="40982-112">Una vez que se han modificado las directivas maestras, la publicación, todas las directivas mediante el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="40982-112">Once the master policies have been modified, publish all polices using the Business Rule Engine Deployment Wizard.</span></span> <span data-ttu-id="40982-113">Utilice la siguiente opción: importar el archivo de directiva o vocabulario a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="40982-113">Use the following option: Import the policy/vocabulary file to database.</span></span>  
  
4.  <span data-ttu-id="40982-114">Haga clic en programas, haga clic en el servidor BizTalk Server \<versión\>, haga clic en el Compositor de reglas de negocios y, a continuación, implementar los seis publicarlos directivas.</span><span class="sxs-lookup"><span data-stu-id="40982-114">Click Programs, click BizTalk Server \<version\>, click Business Rule Composer, and then deploy the six published polices.</span></span>