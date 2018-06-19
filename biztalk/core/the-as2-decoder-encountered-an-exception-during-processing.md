---
title: El descodificador AS2 detectó una excepción durante el procesamiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5f16d2e-e83c-4e2c-84be-41b5ed012dce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2826a938a4f081b8c5895da809e9f16966e25834
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278324"
---
# <a name="the-as2-decoder-encountered-an-exception-during-processing"></a><span data-ttu-id="8dc2e-102">El descodificador AS2 detectó una excepción durante el procesamiento</span><span class="sxs-lookup"><span data-stu-id="8dc2e-102">The AS2 Decoder encountered an exception during processing</span></span>
## <a name="details"></a><span data-ttu-id="8dc2e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8dc2e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8dc2e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8dc2e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8dc2e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8dc2e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="8dc2e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8dc2e-106">Event ID</span></span>|-|  
|<span data-ttu-id="8dc2e-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8dc2e-107">Event Source</span></span>|<span data-ttu-id="8dc2e-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dc2e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="8dc2e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="8dc2e-109">Component</span></span>|<span data-ttu-id="8dc2e-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="8dc2e-110">AS2 Engine</span></span>|  
|<span data-ttu-id="8dc2e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8dc2e-111">Symbolic Name</span></span>|<span data-ttu-id="8dc2e-112">AS2DecoderExceptionEncounteredDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="8dc2e-112">AS2DecoderExceptionEncounteredDuringProcessing</span></span>|  
|<span data-ttu-id="8dc2e-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8dc2e-113">Message Text</span></span>|<span data-ttu-id="8dc2e-114">El descodificador AS2 detectó una excepción durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="8dc2e-114">The AS2 Decoder encountered an exception during processing.</span></span>  <span data-ttu-id="8dc2e-115">Detalles del mensaje y excepción son los siguientes: AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}" MessageType: "{3}" excepción: "\ {4\}"</span><span class="sxs-lookup"><span data-stu-id="8dc2e-115">Details of the message and exception are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" MessageType: "{3}" Exception:"{4}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8dc2e-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="8dc2e-116">Explanation</span></span>  
 <span data-ttu-id="8dc2e-117">Este evento de error,  indica que la canalización de recepción no pudo procesar el mensaje AS2 entrante debido a un problema con el descodificador AS2.</span><span class="sxs-lookup"><span data-stu-id="8dc2e-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming AS2 message because of an issue with the AS2 Decoder.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8dc2e-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8dc2e-118">User Action</span></span>  
 <span data-ttu-id="8dc2e-119">Para resolver este error, compruebe el código de error de AS2 para determinar la naturaleza de la condición de error.</span><span class="sxs-lookup"><span data-stu-id="8dc2e-119">To resolve this error, determine the nature of the error condition by checking the AS2 error code.</span></span> <span data-ttu-id="8dc2e-120">Para obtener más información sobre códigos de error de AS2, consulte el tema "Códigos de error de AS2" en el archivo de Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dc2e-120">For more information on AS2 error codes, see the "AS2 Error Codes" topic in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] help file.</span></span>