---
title: Validar una instancia de mensaje con el esquema XSD | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema XSD
- validating, messages
- messages, validating
- schemas, XSDs
ms.assetid: c4cbf6b4-130d-4e0f-840b-c8008fafac0b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eda0b76b3daff53290264169c5b2effe80a9e5c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="validating-a-message-instance-using-the-schema-xsd"></a><span data-ttu-id="a159f-102">Validar una instancia de mensaje con el esquema XSD</span><span class="sxs-lookup"><span data-stu-id="a159f-102">Validating a Message Instance Using the Schema XSD</span></span>
<span data-ttu-id="a159f-103">Este tema describe cómo validar una instancia de mensaje utilizando uno de los archivos de esquema XSD que Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ha integrado en el archivo de ensamblado Rnpip.</span><span class="sxs-lookup"><span data-stu-id="a159f-103">This topic describes how to validate a message instance using one of the schema XSD files that Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] has built into the RNPIPs assembly file.</span></span>  
  
### <a name="to-validate-a-message-instance-using-the-schema-xsd"></a><span data-ttu-id="a159f-104">Para validar una instancia de mensaje con el esquema XSD</span><span class="sxs-lookup"><span data-stu-id="a159f-104">To validate a message instance using the schema XSD</span></span>  
  
1.  <span data-ttu-id="a159f-105">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="a159f-105">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="a159f-106">En el **archivo**, seleccione **abiertos**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a159f-106">On the **File**, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="a159f-107">Busque  *\<unidad\>*\Program BizTalk \<versión\> Accelerator for RosettaNet\SDK\Schemas, haga clic en **RNPIPs.btproj**, y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="a159f-107">Locate *\<drive\>*\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas, click **RNPIPs.btproj**, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="a159f-108">En el Explorador de soluciones, expanda **Rnpip**, haga clic en el esquema XSD que se desea usar para validar una instancia de mensaje y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a159f-108">In Solution Explorer, expand **RNPIPs**, right-click the schema XSD that you want to use to validate a message instance, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="a159f-109">En el cuadro de diálogo páginas de propiedades, haga clic en **nombre de archivo de instancia de entrada**, busque la carpeta que contiene el archivo, seleccione el archivo XML de instancia de mensaje y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="a159f-109">In the Property Pages dialog box, click **Input Instance Filename**, locate the folder that contains the file, select the message instance XML file, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="a159f-110">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a159f-110">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="a159f-111">En el Explorador de soluciones, haga clic en el esquema XSD que se desea usar para validar una instancia de mensaje y, a continuación, haga clic en **Validar instancia**.</span><span class="sxs-lookup"><span data-stu-id="a159f-111">In Solution Explorer, right-click the schema XSD that you want to use to validate a message instance, and then click **Validate Instance**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a159f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a159f-112">See Also</span></span>  
 <span data-ttu-id="a159f-113">[Modificar una PIP existente en Rnpip](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md) </span><span class="sxs-lookup"><span data-stu-id="a159f-113">[Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md) </span></span>  
 [<span data-ttu-id="a159f-114">Trabajar con PIP</span><span class="sxs-lookup"><span data-stu-id="a159f-114">Working with PIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)