---
title: Configuración de las propiedades del acuerdo de reserva de EDIFACT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.edifactfallback.properties
ms.assetid: fee588db-9ae8-44be-8a8f-9be624dec825
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f71c395926b1a626bce99dfaf2d7d8b333273253
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233236"
---
# <a name="configuring-edifact-fallback-agreement-properties"></a><span data-ttu-id="656cc-102">Configuración de las propiedades de acuerdos de reserva de EDIFACT</span><span class="sxs-lookup"><span data-stu-id="656cc-102">Configuring EDIFACT Fallback Agreement Properties</span></span>
<span data-ttu-id="656cc-103">Las propiedades descritas en esta sección se aplican siempre que se realizan intercambios cifrados de EDIFACT (incluido HIPAA) y que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede determinar el acuerdo al que hacen referencia los intercambios (de entrada o salida).</span><span class="sxs-lookup"><span data-stu-id="656cc-103">The properties described in this section apply whenever EDIFACT-encoded interchanges are exchanged and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot determine the agreement that the interchanges (inbound or outbound) resolve to.</span></span> <span data-ttu-id="656cc-104">En esta sección también se describe la configuración general de reserva común en los mensajes codificados X12 y EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="656cc-104">This section also describes general fallback settings common to both X12 and EDIFACT encoded messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="656cc-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="656cc-105">In This Section</span></span>  
  
-   [<span data-ttu-id="656cc-106">Configuración de EDIFACT y propiedades comunes de reserva para X12 mensajes con codificación</span><span class="sxs-lookup"><span data-stu-id="656cc-106">Configuring Common Fallback Properties for X12 and EDIFACT Encoded Messages</span></span>](../core/configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages.md)  
  
-   [<span data-ttu-id="656cc-107">Configurar propiedades de acuerdo de reserva de EDIFACT para el procesamiento de intercambio</span><span class="sxs-lookup"><span data-stu-id="656cc-107">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)  
  
-   [<span data-ttu-id="656cc-108">Configurar la configuración de propiedades de acuerdo de reserva de EDIFACT para la transacción</span><span class="sxs-lookup"><span data-stu-id="656cc-108">Configuring EDIFACT Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)  
  
## <a name="see-also"></a><span data-ttu-id="656cc-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="656cc-109">See Also</span></span>  
 [<span data-ttu-id="656cc-110">Configurar propiedades del acuerdo de reserva o globales</span><span class="sxs-lookup"><span data-stu-id="656cc-110">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)