---
title: 'Paso 3: Probar el Application2 migrados | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Send IDOC)
- migration
ms.assetid: 8dc0d127-71ce-4668-a3bf-c893a8f6848d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc49906e58e549a8ed9c90446b011dc3b51e0a45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017820"
---
# <a name="step-3-test-the-migrated-application"></a><span data-ttu-id="dc177-102">Paso 3: Probar la aplicación migrada</span><span class="sxs-lookup"><span data-stu-id="dc177-102">Step 3: Test the Migrated Application</span></span>
<span data-ttu-id="dc177-103">![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="dc177-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="dc177-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="dc177-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="dc177-105">**Objetivo:** en este paso, probará la aplicación migrada enviando un IDOC de archivo sin formato mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc177-105">**Objective:** In this step, you will test the migrated application by sending a flat-file IDOC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dc177-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dc177-106">Prerequisites</span></span>  
  
- <span data-ttu-id="dc177-107">Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="dc177-107">Configure the BizTalk application by mapping the logical ports in the BizTalk orchestration to physical ports in the BizTalk Server Administration console.</span></span>  
  
- <span data-ttu-id="dc177-108">Configurar la aplicación de BizTalk para utilizar el puerto de envío WCF-custom basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc177-108">Configure the BizTalk application to use the WCF-custom send port for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
### <a name="to-test-the-migrated-application"></a><span data-ttu-id="dc177-109">Para probar la aplicación migrada</span><span class="sxs-lookup"><span data-stu-id="dc177-109">To test the migrated application</span></span>  
  
1.  <span data-ttu-id="dc177-110">En la carpeta SendIDOC_Migration, copie el archivo BOMDOC.txt.</span><span class="sxs-lookup"><span data-stu-id="dc177-110">From the SendIDOC_Migration folder, copy the BOMDOC.txt file.</span></span> <span data-ttu-id="dc177-111">Este es el IDOC de archivo sin formato para enviarse al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="dc177-111">This is the flat-file IDOC to be sent to the SAP system.</span></span>  
  
2.  <span data-ttu-id="dc177-112">Pegar el IDOC de archivo sin formato a la carpeta que se asigna al archivo de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="dc177-112">Paste the flat-file IDOC to the folder that is mapped to the file receive location.</span></span>  
  
3.  <span data-ttu-id="dc177-113">La orquestación consume el archivo y envía el IDOC al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="dc177-113">The orchestration consumes the file and sends the IDOC to the SAP system.</span></span> <span data-ttu-id="dc177-114">Compruebe si hay errores en el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc177-114">Verify if there are any errors in the event viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc177-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc177-115">See Also</span></span>  
 [<span data-ttu-id="dc177-116">Tutorial 3: Migración de un proyecto de BizTalk SAP IDOC de envío</span><span class="sxs-lookup"><span data-stu-id="dc177-116">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)