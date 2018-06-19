---
title: Establecer los desplazamientos para la validación de cantidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- amounts, validating
- validating, amounts
- amounts, offsets
- offsets
ms.assetid: 39d5510c-52e6-4fd9-9632-582b508f04d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cfae474407daa7dd3c0b95db3fed076a581cf1c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961258"
---
# <a name="setting-offsets-for-amount-validation"></a><span data-ttu-id="e9b50-102">Configuración de desplazamientos para la validación de cantidad</span><span class="sxs-lookup"><span data-stu-id="e9b50-102">Setting Offsets for Amount Validation</span></span>
<span data-ttu-id="e9b50-103">Las reglas de uso para los campos de cantidad de tipos de mensaje MT102, MT103 y MT103PLUS se validan las reglas en las directivas de validación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e9b50-103">The usage rules for Amount fields in message types MT102, MT103, and MT103PLUS are validated by rules in their respective validation policies.</span></span> <span data-ttu-id="e9b50-104">Los campos de cantidad pueden coincidir exactamente o pueden comprobar que está dentro del intervalo de cantidades.</span><span class="sxs-lookup"><span data-stu-id="e9b50-104">The Amount fields can be matched exactly or can be validated to be within a range of amounts.</span></span>  
  
 <span data-ttu-id="e9b50-105">Para habilitar la validación dentro de un intervalo, se especifica un porcentaje de desplazamiento en la llamada al método en la directiva de validación pertinentes.</span><span class="sxs-lookup"><span data-stu-id="e9b50-105">To enable validation within a range, you specify an offset percentage in the method call in the relevant validation policy.</span></span> <span data-ttu-id="e9b50-106">Por ejemplo, si la cantidad que se establece para el campo es 100 y el porcentaje de desplazamiento es 10 por ciento, una cantidad válida sería cualquier valor entre 90 y 110, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="e9b50-106">For example, if the amount that you set for the field is 100, and the offset percentage is 10 percent, a valid amount would be any value from 90 to 110, inclusive.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="e9b50-107">proporciona esta compatibilidad para los tipos de mensaje MT102, MT102PLUS y MT103.</span><span class="sxs-lookup"><span data-stu-id="e9b50-107"> provides this support for the MT102, MT102PLUS, and MT103 message types.</span></span>  
  
 <span data-ttu-id="e9b50-108">Se especifica el porcentaje de desplazamiento en la vista la **IsValidSettlementAmount** o **IsValidInterbankSettledAmount** método en la directiva de validación.</span><span class="sxs-lookup"><span data-stu-id="e9b50-108">The offset percentage is specified in either the **IsValidSettlementAmount** or **IsValidInterbankSettledAmount** method in the validation policy.</span></span> <span data-ttu-id="e9b50-109">El **IsValidSettlementAmount** método implementa la regla de uso de los campos de cantidad de mensajes MT102 y MT102PLUS.</span><span class="sxs-lookup"><span data-stu-id="e9b50-109">The **IsValidSettlementAmount** method implements the usage rule for Amount fields of MT102 and MT102PLUS messages.</span></span> <span data-ttu-id="e9b50-110">El **IsValidInterbankSettledAmount** método implementa la regla de uso de los campos de cantidad de mensajes de MT103.</span><span class="sxs-lookup"><span data-stu-id="e9b50-110">The **IsValidInterbankSettledAmount** method implements the usage rule for Amount fields of MT103 messages.</span></span> <span data-ttu-id="e9b50-111">Especifique el porcentaje de desplazamiento en el argumento OffsetPercent, que es el décimo argumento de uno de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="e9b50-111">You specify the offset percentage in the OffsetPercent argument, which is the tenth argument of either of those methods.</span></span>  
  
 <span data-ttu-id="e9b50-112">Cuando se establece, el desplazamiento de porcentaje se aplica a los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9b50-112">When set, the percentage offset applies to the following fields:</span></span>  
  
|<span data-ttu-id="e9b50-113">Tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="e9b50-113">Message type</span></span>|<span data-ttu-id="e9b50-114">Validada con desplazamientos de campos</span><span class="sxs-lookup"><span data-stu-id="e9b50-114">Fields validated with offsets</span></span>|  
|------------------|-----------------------------------|  
|<span data-ttu-id="e9b50-115">MT102 o MT102PLUS</span><span class="sxs-lookup"><span data-stu-id="e9b50-115">MT102 or MT102PLUS</span></span>|<span data-ttu-id="e9b50-116">32</span><span class="sxs-lookup"><span data-stu-id="e9b50-116">32</span></span><br /><br /> <span data-ttu-id="e9b50-117">33B</span><span class="sxs-lookup"><span data-stu-id="e9b50-117">33B</span></span>|  
|<span data-ttu-id="e9b50-118">MT103</span><span class="sxs-lookup"><span data-stu-id="e9b50-118">MT103</span></span>|<span data-ttu-id="e9b50-119">19, secuencia de C</span><span class="sxs-lookup"><span data-stu-id="e9b50-119">19, Sequence C</span></span><br /><br /> <span data-ttu-id="e9b50-120">31a, secuencia de C</span><span class="sxs-lookup"><span data-stu-id="e9b50-120">31A, Sequence C</span></span><br /><br /> <span data-ttu-id="e9b50-121">72G</span><span class="sxs-lookup"><span data-stu-id="e9b50-121">72G</span></span>|  
  
### <a name="to-set-an-offset-percentage"></a><span data-ttu-id="e9b50-122">Para establecer un porcentaje de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="e9b50-122">To set an offset percentage</span></span>  
  
1.  <span data-ttu-id="e9b50-123">Abra un editor de texto, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="e9b50-123">Open a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="e9b50-124">En el editor, vaya a la ubicación de la directiva de validación de mensaje en el que desea establecer un porcentaje de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="e9b50-124">In the editor, browse to the location of the message validation policy in which you want to set an offset percentage.</span></span> <span data-ttu-id="e9b50-125">Por ejemplo, puede encontrar la directiva de validación de mensajes para el tipo de mensaje MT103, MT103_Validation_Policy.xml, en  *\<unidad\>*: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \< versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category 1\MT103.</span><span class="sxs-lookup"><span data-stu-id="e9b50-125">For example, you can find the message validation policy for the MT103 message type, MT103_Validation_Policy.xml, in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103.</span></span> <span data-ttu-id="e9b50-126">Abra la directiva de validación.</span><span class="sxs-lookup"><span data-stu-id="e9b50-126">Open the validation policy.</span></span>  
  
3.  <span data-ttu-id="e9b50-127">En la directiva, buscar en IsValidSettlementAmount para mensajes MT102 y MT102PLUS o IsValidInterbankSettledAmount MT103 mensajes.</span><span class="sxs-lookup"><span data-stu-id="e9b50-127">In the policy, search on IsValidSettlementAmount for MT102 and MT102PLUS messages or IsValidInterbankSettledAmount for MT103 messages.</span></span>  
  
4.  <span data-ttu-id="e9b50-128">Cuenta atrás para el décimo argumento.</span><span class="sxs-lookup"><span data-stu-id="e9b50-128">Count down to the tenth argument.</span></span> <span data-ttu-id="e9b50-129">Especifique el porcentaje de la posición de desplazamiento en el argumento.</span><span class="sxs-lookup"><span data-stu-id="e9b50-129">Enter the percentage of the offset in the argument.</span></span>  
  
5.  <span data-ttu-id="e9b50-130">Guarde el archivo y, a continuación, cierre el editor.</span><span class="sxs-lookup"><span data-stu-id="e9b50-130">Save the file, and then close the editor.</span></span>