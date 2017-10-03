---
title: "Cómo etiquetar y comentar un Functoid | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.functiod.general
ms.assetid: 58ff3a07-cbb6-4817-b301-d2b434ed2ad9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fccdeefa35f9abb5a0c3158dba518d524811c611
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-label-and-comment-a-functoid"></a><span data-ttu-id="d0bca-102">Agregación de etiquetas y comentarios en un functoid</span><span class="sxs-lookup"><span data-stu-id="d0bca-102">How to Label and Comment a Functoid</span></span>
<span data-ttu-id="d0bca-103">Las etiquetas y comentarios resultan útiles para documentar la finalidad de un functoid o vínculo en una asignación.</span><span class="sxs-lookup"><span data-stu-id="d0bca-103">Labels and comments are helpful to document the purpose of a functoid or a link in a map.</span></span> <span data-ttu-id="d0bca-104">Puede usar el **etiqueta** propiedad para proporcionar un nombre para un functoid.</span><span class="sxs-lookup"><span data-stu-id="d0bca-104">You can use the **Label** property to provide a name for a functoid.</span></span> <span data-ttu-id="d0bca-105">El **comentarios** propiedad le permite proporcionar información adicional acerca del functoid, normalmente información relevante sobre la operación que se va a realizar en él.</span><span class="sxs-lookup"><span data-stu-id="d0bca-105">The **Comments** property enables you to provide additional information about the functoid, typically relevant information about the operation being performed by it.</span></span>  
  
 <span data-ttu-id="d0bca-106">En la siguiente ilustración se muestran la etiqueta y los comentarios de un functoid.</span><span class="sxs-lookup"><span data-stu-id="d0bca-106">The following figure shows the label and comments for a functoid.</span></span> <span data-ttu-id="d0bca-107">El functoid agrega dos entradas (Field1 y Field3) desde el esquema de origen y envía el resultado al Field4 en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="d0bca-107">The functoid adds two inputs (Field1 and Field3) from the source schema and outputs the result to Field4 in the target schema.</span></span> <span data-ttu-id="d0bca-108">En este ejemplo, la etiqueta del functoid es “Add Field1 and Field3” y el comentario es “The addition is an output to Field4”.</span><span class="sxs-lookup"><span data-stu-id="d0bca-108">In this example, the functoid label is “Add Field1 and Field3” and the comment is “The addition is an output to Field4”.</span></span>  
  
 <span data-ttu-id="d0bca-109">![Insertar etiquetas de functoid y comentarios](../core/media/label.gif "Label_")</span><span class="sxs-lookup"><span data-stu-id="d0bca-109">![Inserting functoid labels and comments](../core/media/label.gif "Label_")</span></span>  
  
 <span data-ttu-id="d0bca-110">Como un functoid puede formar parte de una asignación muy compleja, es importarle etiquetarlo debidamente y proporcionar además comentarios relevantes.</span><span class="sxs-lookup"><span data-stu-id="d0bca-110">Because a functoid can be a part of very complex mapping, it is important to label it properly and also to provide relevant comments.</span></span> <span data-ttu-id="d0bca-111">Puede etiquetar tanto functoids como vínculos.</span><span class="sxs-lookup"><span data-stu-id="d0bca-111">You can label both functoids and links.</span></span> <span data-ttu-id="d0bca-112">Para obtener información sobre cómo etiquetar un vínculo, vea [cómo etiquetar un vínculo](../core/how-to-label-a-link.md).</span><span class="sxs-lookup"><span data-stu-id="d0bca-112">For information on how to label a link, see [How to Label a Link](../core/how-to-label-a-link.md).</span></span>  
  
 <span data-ttu-id="d0bca-113">Puede etiquetar y comentar un functoid de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="d0bca-113">You can label and comment a functoid in the following ways:</span></span>  
  
-   <span data-ttu-id="d0bca-114">Mediante el uso de la **configurar \<Functoid > Functoid** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d0bca-114">By using the **Configure \<Functoid> Functoid** dialog box.</span></span>  
  
-   <span data-ttu-id="d0bca-115">Mediante el uso de la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="d0bca-115">By using the **Properties** window.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d0bca-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d0bca-116">Prerequisites</span></span>  
 <span data-ttu-id="d0bca-117">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d0bca-117">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-label-and-comment-a-functoid-from-configure-dialog-box"></a><span data-ttu-id="d0bca-118">Para etiquetar y comentar un functoid desde el cuadro de diálogo Configurar</span><span class="sxs-lookup"><span data-stu-id="d0bca-118">To label and comment a functoid from Configure dialog box</span></span>  
  
1.  <span data-ttu-id="d0bca-119">Haga clic en el functoid que desea etiquetar y comentar y, a continuación, haga clic en **configurar entradas de Functoid**.</span><span class="sxs-lookup"><span data-stu-id="d0bca-119">Right-click the functoid you want to label and comment, and then click **Configure Functoid Inputs**.</span></span>  
  
2.  <span data-ttu-id="d0bca-120">En el **configurar \<Functoid > Functoid** cuadro de diálogo, haga clic en el **etiqueta y comentarios** ficha.</span><span class="sxs-lookup"><span data-stu-id="d0bca-120">In the **Configure \<Functoid> Functoid** dialog box, click the **Label and Comments** tab.</span></span>  
  
3.  <span data-ttu-id="d0bca-121">Escriba la información siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0bca-121">Enter the following information, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="d0bca-122">**Etiqueta:** escriba el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="d0bca-122">**Label –** Enter the new name.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="d0bca-123">El número máximo de caracteres permitido es 256.</span><span class="sxs-lookup"><span data-stu-id="d0bca-123">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="d0bca-124">Si se especifica una cadena con más de 256 caracteres, se aceptan los primeros 256 caracteres y el resto se descartan.</span><span class="sxs-lookup"><span data-stu-id="d0bca-124">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
    -   <span data-ttu-id="d0bca-125">**Comentarios:** introduzca comentarios para el functoid.</span><span class="sxs-lookup"><span data-stu-id="d0bca-125">**Comments –** Enter the comments for the functoid.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="d0bca-126">El número máximo de caracteres permitido es 1024.</span><span class="sxs-lookup"><span data-stu-id="d0bca-126">The maximum number of characters allowed is 1024.</span></span> <span data-ttu-id="d0bca-127">Si se especifica una cadena con más de 1024 caracteres, se aceptan los primeros 1024 caracteres y el resto se descartan.</span><span class="sxs-lookup"><span data-stu-id="d0bca-127">If a string with more than 1024 characters is specified, the first 1024 characters are accepted and the rest are discarded.</span></span>  
  
### <a name="to-label-and-comment-a-functoid-from-properties-window"></a><span data-ttu-id="d0bca-128">Procedimiento para etiquetar y comentar un functoid desde la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="d0bca-128">To label and comment a functoid from Properties window</span></span>  
  
1.  <span data-ttu-id="d0bca-129">Seleccione el functoid que desea etiquetar y comentar.</span><span class="sxs-lookup"><span data-stu-id="d0bca-129">Select the functoid you want to label and comment.</span></span>  
  
2.  <span data-ttu-id="d0bca-130">En el **propiedades** ventana, escriba la información siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0bca-130">In the **Properties** window, enter the following information, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="d0bca-131">**Etiqueta:** escriba el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="d0bca-131">**Label –** Enter the new name.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="d0bca-132">El número máximo de caracteres permitido es 256.</span><span class="sxs-lookup"><span data-stu-id="d0bca-132">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="d0bca-133">Si se especifica una cadena con más de 256 caracteres, se aceptan los primeros 256 caracteres y el resto se descartan.</span><span class="sxs-lookup"><span data-stu-id="d0bca-133">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
    -   <span data-ttu-id="d0bca-134">**Comentarios:** introduzca comentarios para el functoid.</span><span class="sxs-lookup"><span data-stu-id="d0bca-134">**Comments –** Enter the comments for the functoid.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="d0bca-135">El número máximo de caracteres permitido es 1024.</span><span class="sxs-lookup"><span data-stu-id="d0bca-135">The maximum number of characters allowed is 1024.</span></span> <span data-ttu-id="d0bca-136">Si se especifica una cadena con más de 1024 caracteres, se aceptan los primeros 1024 caracteres y el resto se descartan.</span><span class="sxs-lookup"><span data-stu-id="d0bca-136">If a string with more than 1024 characters is specified, the first 1024 characters are accepted and the rest are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0bca-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0bca-137">See Also</span></span>  
 [<span data-ttu-id="d0bca-138">Editar propiedades de Functoid y parámetros de entrada</span><span class="sxs-lookup"><span data-stu-id="d0bca-138">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)