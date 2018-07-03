---
title: 'Paso 3: Probar el Application5 migrados | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Receive IDOC)
- migration
ms.assetid: 3ad15069-1556-4c0a-8bfd-86704d40c586
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195b150dcbc3edcd1bfe0a18a17c6fe73cb4f50b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009149"
---
# <a name="step-3-test-the-migrated-application"></a><span data-ttu-id="6572a-102">Paso 3: Probar la aplicación migrada</span><span class="sxs-lookup"><span data-stu-id="6572a-102">Step 3: Test the Migrated Application</span></span>
<span data-ttu-id="6572a-103">![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="6572a-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="6572a-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="6572a-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="6572a-105">**Objetivo:** en este paso, probará la aplicación migrada al recibir un IDOC de archivo sin formato mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6572a-105">**Objective:** In this step, you will test the migrated application by receiving a flat-file IDOC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6572a-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6572a-106">Prerequisites</span></span>  
  
- <span data-ttu-id="6572a-107">Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6572a-107">Configure the BizTalk application by mapping the logical ports in the BizTalk orchestration to physical ports in the BizTalk Server Administration console.</span></span>  
  
- <span data-ttu-id="6572a-108">Configurar BizTalk aplicación para que use el WCF-Custom puerto de recepción para la basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6572a-108">Configure the BizTalk application to use the WCF-Custom receive port for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
### <a name="to-test-the-migrated-application"></a><span data-ttu-id="6572a-109">Para probar la aplicación migrada</span><span class="sxs-lookup"><span data-stu-id="6572a-109">To test the migrated application</span></span>  
  
1.  <span data-ttu-id="6572a-110">Inicie la GUI de SAP y conéctese al sistema SAP que especificó en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="6572a-110">Start the SAP GUI, and connect to the SAP system that you specified in the connection URI.</span></span>  
  
2.  <span data-ttu-id="6572a-111">Ejecute SE37 e invocar un módulo de función de SAP que se envía un IDOC a un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="6572a-111">Run SE37, and invoke a function module in SAP that sends an IDOC to an external system.</span></span> <span data-ttu-id="6572a-112">Asegúrese de que enviar el IDOC con el mismo identificador de programa que se especifica en el URI de conexión de puerto de recepción personalizada de WCF.</span><span class="sxs-lookup"><span data-stu-id="6572a-112">Make sure you send the IDOC using the same program ID that is specified in the connection URI for the WCF-Custom receive port.</span></span>  
  
3.  <span data-ttu-id="6572a-113">Busque el IDOC entrante en la ubicación del archivo especificado como parte de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="6572a-113">Look for the inbound IDOC at the file location specified as part of the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6572a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6572a-114">See Also</span></span>  
 [<span data-ttu-id="6572a-115">Tutorial 4: Migración de un proyecto de BizTalk IDOC de SAP de recepción</span><span class="sxs-lookup"><span data-stu-id="6572a-115">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)