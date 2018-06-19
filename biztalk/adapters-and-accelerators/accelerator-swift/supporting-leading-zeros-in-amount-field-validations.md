---
title: Compatibilidad con los ceros iniciales de validaciones de campo de cantidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- amounts, amount fields
- amounts, leading zeros
- validating, amount fields
ms.assetid: 7c202422-019f-43da-9c2a-4b9fdf0b2859
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3559b63ec7588fa2d7451779947a476cf19b7bf0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961370"
---
# <a name="supporting-leading-zeros-in-amount-field-validations"></a><span data-ttu-id="91a49-102">Compatibilidad con los ceros iniciales de validaciones de campo de cantidad</span><span class="sxs-lookup"><span data-stu-id="91a49-102">Supporting Leading Zeros in Amount Field Validations</span></span>
<span data-ttu-id="91a49-103">Las directivas de validación de algunos tipos de mensaje realizan validaciones en los campos de cantidad.</span><span class="sxs-lookup"><span data-stu-id="91a49-103">The validation policies of some message types perform validations on Amount fields.</span></span> <span data-ttu-id="91a49-104">Para habilitar los ceros a la izquierda en los campos de cantidad, debe modificar la directiva de validación para el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="91a49-104">To enable leading zeros in Amount fields, you must edit the validation policy for the message type.</span></span> <span data-ttu-id="91a49-105">Puede crear una nueva versión de la directiva de validación de forma predeterminada y editar el argumento en el Compositor de reglas de negocios, o puede modificar la directiva predeterminada manualmente en un editor de texto antes de implementa la directiva.</span><span class="sxs-lookup"><span data-stu-id="91a49-105">You can create a new version of the default validation policy, and edit the argument in the Business Rule Composer, or you can edit the default policy manually in a text editor before the policy is deployed.</span></span>  
  
 <span data-ttu-id="91a49-106">En la tabla siguiente se enumera los métodos que habilitan o deshabilitan ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="91a49-106">The following table lists the methods that enable or disable leading zeros.</span></span> <span data-ttu-id="91a49-107">La tabla también indica el número ordinal del argumento que se debe establecer en el método.</span><span class="sxs-lookup"><span data-stu-id="91a49-107">The table also indicates the ordinal number of the argument that you need to set in the method.</span></span> <span data-ttu-id="91a49-108">Establézcala en True para permitir ceros a la izquierda o en False para deshabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="91a49-108">Set it to True to enable leading zeros, or to False to disable them.</span></span>  
  
|<span data-ttu-id="91a49-109">Método</span><span class="sxs-lookup"><span data-stu-id="91a49-109">Method</span></span>|<span data-ttu-id="91a49-110">Número de argumento</span><span class="sxs-lookup"><span data-stu-id="91a49-110">Argument number</span></span>|  
|------------|---------------------|  
|<span data-ttu-id="91a49-111">**CheckValidAmount**</span><span class="sxs-lookup"><span data-stu-id="91a49-111">**CheckValidAmount**</span></span>|<span data-ttu-id="91a49-112">6</span><span class="sxs-lookup"><span data-stu-id="91a49-112">6</span></span>|  
|<span data-ttu-id="91a49-113">**CheckCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="91a49-113">**CheckCurrencyAmount**</span></span>|<span data-ttu-id="91a49-114">4</span><span class="sxs-lookup"><span data-stu-id="91a49-114">4</span></span>|  
|<span data-ttu-id="91a49-115">**CheckValidSignCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="91a49-115">**CheckValidSignCurrencyAmount**</span></span>|<span data-ttu-id="91a49-116">3</span><span class="sxs-lookup"><span data-stu-id="91a49-116">3</span></span>|  
|<span data-ttu-id="91a49-117">**CheckValidSignDateCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="91a49-117">**CheckValidSignDateCurrencyAmount**</span></span>|<span data-ttu-id="91a49-118">4</span><span class="sxs-lookup"><span data-stu-id="91a49-118">4</span></span>|  
|<span data-ttu-id="91a49-119">**IsValidTransactionDetailsCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="91a49-119">**IsValidTransactionDetailsCurrencyAmount**</span></span>|<span data-ttu-id="91a49-120">4</span><span class="sxs-lookup"><span data-stu-id="91a49-120">4</span></span>|  
  
 <span data-ttu-id="91a49-121">Cada método en la tabla anterior se encuentra en una o varias directivas de validación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="91a49-121">Each method in the preceding table is contained in one or more message validation policies.</span></span> <span data-ttu-id="91a49-122">Para establecer el argumento en una directiva, debe buscar en el nombre del método para comprobar si la directiva lo contiene.</span><span class="sxs-lookup"><span data-stu-id="91a49-122">To set the argument in a policy, you must search on the method name to verify whether the policy contains it.</span></span> <span data-ttu-id="91a49-123">Un método puede aparecer varias veces en la directiva de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="91a49-123">A method may appear multiple times in a message's policy.</span></span>  
  
### <a name="to-enable-or-disable-leading-zeros"></a><span data-ttu-id="91a49-124">Para habilitar o deshabilitar los ceros a la izquierda</span><span class="sxs-lookup"><span data-stu-id="91a49-124">To enable or disable leading zeros</span></span>  
  
1.  <span data-ttu-id="91a49-125">Abra un editor de texto, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="91a49-125">Open a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="91a49-126">En el editor, vaya a la ubicación de la directiva de validación de mensaje en el que desea habilitar o deshabilitar los ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="91a49-126">In the editor, browse to the location of the message validation policy in which you want to enable or disable leading zeros.</span></span> <span data-ttu-id="91a49-127">Por ejemplo, puede encontrar la directiva de validación de mensajes para el tipo de mensaje MT103, MT103_Validation_Policy.xml, en  *\<unidad\>*: / programa archivos/Microsoft BizTalk Accelerator for SWIFT/SWIFT mensajes / Categoría 1/MT103.</span><span class="sxs-lookup"><span data-stu-id="91a49-127">For example, you can find the message validation policy for the MT103 message type, MT103_Validation_Policy.xml, in *\<drive\>*:/Program Files/Microsoft BizTalk Accelerator for SWIFT/SWIFT Messages/Category 1/MT103.</span></span> <span data-ttu-id="91a49-128">Abra la directiva de validación.</span><span class="sxs-lookup"><span data-stu-id="91a49-128">Open the validation policy.</span></span>  
  
3.  <span data-ttu-id="91a49-129">En la directiva, busque en el **CheckValidAmount** método.</span><span class="sxs-lookup"><span data-stu-id="91a49-129">In the policy, search on the **CheckValidAmount** method.</span></span>  
  
4.  <span data-ttu-id="91a49-130">Si se encuentra el método, se cuentan hacia abajo para el argumento correspondiente.</span><span class="sxs-lookup"><span data-stu-id="91a49-130">If you find the method, count down to the appropriate argument.</span></span> <span data-ttu-id="91a49-131">Por ejemplo, para la **CheckValidAmount** recuento hasta el sexto argumento del método.</span><span class="sxs-lookup"><span data-stu-id="91a49-131">For example, for the **CheckValidAmount** method, count down to the sixth argument.</span></span> <span data-ttu-id="91a49-132">Establezca el argumento en **True** para habilitar ceros iniciales ni False para deshabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="91a49-132">Set the argument to **True** to enable leading zeros or False to disable them.</span></span>  
  
5.  <span data-ttu-id="91a49-133">Repita los pasos 3 y 4 para cada método en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="91a49-133">Repeat steps 3 and 4 for each method in the preceding table.</span></span>  
  
6.  <span data-ttu-id="91a49-134">Guarde el archivo y, a continuación, cierre el editor.</span><span class="sxs-lookup"><span data-stu-id="91a49-134">Save the file, and then close the editor.</span></span>