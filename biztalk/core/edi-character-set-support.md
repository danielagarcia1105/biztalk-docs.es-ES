---
title: Compatibilidad con juego de caracteres de EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4f4492b-8cbe-48ed-810a-3e73e1cb5996
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c1463d8a06ab5da89306aababfe19362d6308dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-character-set-support"></a><span data-ttu-id="558d9-102">Compatibilidad de juegos de caracteres de EDI</span><span class="sxs-lookup"><span data-stu-id="558d9-102">EDI Character Set Support</span></span>
<span data-ttu-id="558d9-103">En este tema se indican qué juegos de caracteres se admiten en las características EDI de [!INCLUDE[prague](../includes/prague-md.md)].</span><span class="sxs-lookup"><span data-stu-id="558d9-103">This topic indicates which character sets are supported in the EDI features of [!INCLUDE[prague](../includes/prague-md.md)].</span></span>  
  
|<span data-ttu-id="558d9-104">Codificación EDI</span><span class="sxs-lookup"><span data-stu-id="558d9-104">EDI Encoding</span></span>|<span data-ttu-id="558d9-105">Juegos de caracteres admitidos</span><span class="sxs-lookup"><span data-stu-id="558d9-105">Supported Character Sets</span></span>|  
|------------------|------------------------------|  
|<span data-ttu-id="558d9-106">X 12 (incluida HIPAA)</span><span class="sxs-lookup"><span data-stu-id="558d9-106">X12 (including HIPAA)</span></span>|<span data-ttu-id="558d9-107">X12: juego de caracteres básico (subjuego de ASCII)</span><span class="sxs-lookup"><span data-stu-id="558d9-107">X12 - Basic character set (subset of ASCII)</span></span>|  
|-|<span data-ttu-id="558d9-108">X12: juego de caracteres ampliado (subjuego de ASCII que también incluye caracteres ISO8859-1)</span><span class="sxs-lookup"><span data-stu-id="558d9-108">X12- Extended character set (subset of ASCII and also includes ISO8859-1 chars)</span></span>|  
|-|<span data-ttu-id="558d9-109">UTF8/UNICODE</span><span class="sxs-lookup"><span data-stu-id="558d9-109">UTF8/UNICODE</span></span>|  
|<span data-ttu-id="558d9-110">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="558d9-110">EDIFACT</span></span>|<span data-ttu-id="558d9-111">UNOA</span><span class="sxs-lookup"><span data-stu-id="558d9-111">UNOA</span></span>|  
|-|<span data-ttu-id="558d9-112">UNOB</span><span class="sxs-lookup"><span data-stu-id="558d9-112">UNOB</span></span>|  
|-|<span data-ttu-id="558d9-113">UNOC - ISO 8859-1: procesamiento de información - parte 1: alfabeto latino N.º</span><span class="sxs-lookup"><span data-stu-id="558d9-113">UNOC- ISO 8859-1 : Information processing - Part 1: Latin alphabet No.</span></span> <span data-ttu-id="558d9-114">1</span><span class="sxs-lookup"><span data-stu-id="558d9-114">1</span></span>|  
|-|<span data-ttu-id="558d9-115">KECA - KS_C_5601-1987 (página de códigos 949 de Windows)</span><span class="sxs-lookup"><span data-stu-id="558d9-115">KECA - KS_C_5601-1987 (Windows 949 Code page)</span></span>|  
|-|<span data-ttu-id="558d9-116">UNOX (ISO2022 – JP)</span><span class="sxs-lookup"><span data-stu-id="558d9-116">UNOX (ISO2022 – JP)</span></span>|  
|-|<span data-ttu-id="558d9-117">Datos codificados en UTF8 UNOY - **Nota:** los caracteres UNOD a UNOK establece que admiten UTF8 también se admiten los datos codificados.</span><span class="sxs-lookup"><span data-stu-id="558d9-117">UNOY- UTF8 encoded data **Note:**  The UNOD through UNOK character sets that support UTF8 encoded data are also supported.</span></span>|  
  
## <a name="setting-the-edi-character-set"></a><span data-ttu-id="558d9-118">Configurar el juego de caracteres de EDI</span><span class="sxs-lookup"><span data-stu-id="558d9-118">Setting the EDI Character Set</span></span>  
 <span data-ttu-id="558d9-119">En el caso de intercambios con codificación X12, se puede establecer el juego de caracteres para una canalización configurando la propiedad de canalización CharacterSet.</span><span class="sxs-lookup"><span data-stu-id="558d9-119">For X12 encoded interchanges, you can set the character set for a pipeline by setting the CharacterSet pipeline property.</span></span> <span data-ttu-id="558d9-120">Para obtener más información, consulte [configurar propiedades de canalización de EDI](../core/configuring-edi-pipeline-properties.md).</span><span class="sxs-lookup"><span data-stu-id="558d9-120">For more information, see [Configuring EDI Pipeline Properties](../core/configuring-edi-pipeline-properties.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="558d9-121">Existe un control de juego de caracteres de X12 en la página Generación de sobres de intercambio X12 del cuadro de diálogo de propiedades X12 de EDI de la consola de administración de BizTalk Server, pero dicho control solo se usa para validar los valores especificados de las propiedades del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="558d9-121">There is an X12 character set control in the X12 Interchange Envelope Generation page of the X12 EDI Properties dialog box in the BizTalk Server Administration console, but that control is only used to validate the values entered for the properties in the EDI Properties dialog box.</span></span>  
  
 <span data-ttu-id="558d9-122">En el caso de intercambios con codificación EDIFACT, se puede establecer el conjunto de caracteres para una entidad configurando la propiedad de entidad UNB1.1 en la página de propiedades Definición de segmento UNB para la entidad como receptor de intercambio.</span><span class="sxs-lookup"><span data-stu-id="558d9-122">For EDIFACT encoded interchanges, you can set the character set for a party by setting the UNB1.1 party property in the UNB Segment Definition property page for the party as interchange receiver.</span></span> <span data-ttu-id="558d9-123">El valor del campo UNB1.1 que figura en el encabezado del intercambio determina la codificación empleada en un intercambio entrante.</span><span class="sxs-lookup"><span data-stu-id="558d9-123">The encoding used in an incoming interchange is determined by the value of the UNB1.1 field in the header of the interchange.</span></span> <span data-ttu-id="558d9-124">Para obtener más información, consulte [configuración de sobres (configuración del conjunto de transacciones EDIFACT)](../core/configuring-envelopes-edifact-transaction-set-settings.md).</span><span class="sxs-lookup"><span data-stu-id="558d9-124">For more information, see [Configuring Envelopes (EDIFACT-Transaction Set Settings)](../core/configuring-envelopes-edifact-transaction-set-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="558d9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="558d9-125">See Also</span></span>  
 <span data-ttu-id="558d9-126">[Configurar propiedades de canalización EDI](../core/configuring-edi-pipeline-properties.md) </span><span class="sxs-lookup"><span data-stu-id="558d9-126">[Configuring EDI Pipeline Properties](../core/configuring-edi-pipeline-properties.md) </span></span>  
 [<span data-ttu-id="558d9-127">Configuración de sobres (configuración del conjunto de transacciones EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="558d9-127">Configuring Envelopes (EDIFACT-Transaction Set Settings)</span></span>](../core/configuring-envelopes-edifact-transaction-set-settings.md)