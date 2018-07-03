---
title: Traducir parámetros de consulta SAP en los comandos EXECQUERY de mySAP adaptador en BizTalk | Microsoft Docs
description: Guía para traducir consultas SAP para EXECQUERY, con ejemplos
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a545e20-2607-4946-a60d-0a227b86d093
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8ffd480e952e0df7114a93f6cb2a5baf631ad96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021699"
---
# <a name="translate-sap-query-parameters-into-execquery-command"></a><span data-ttu-id="f6fdf-103">Traducir parámetros de consulta SAP en el comando EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="f6fdf-103">Translate SAP query parameters into EXECQUERY command</span></span>
<span data-ttu-id="f6fdf-104">Explica cómo se traducen los parámetros de una consulta en un texto de comando EXECQUERY.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-104">Explains how the parameters of a query translate into an EXECQUERY command text.</span></span> <span data-ttu-id="f6fdf-105">En este tema se usa el ejemplo de una consulta personalizada de SAP, ZQUERY_TST_NEW.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-105">This topic uses the example of a custom SAP query, ZQUERY_TST_NEW.</span></span>  
  
## <a name="open-the-query-in-sap-gui"></a><span data-ttu-id="f6fdf-106">Abra la consulta en la GUI de SAP</span><span class="sxs-lookup"><span data-stu-id="f6fdf-106">Open the Query in SAP GUI</span></span>  
 <span data-ttu-id="f6fdf-107">Realice los pasos siguientes para abrir la consulta en SAP.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-107">Perform the following steps to open the query in SAP.</span></span> <span data-ttu-id="f6fdf-108">Los pasos que se proporcionan aquí son para consulta ZQUERY_TST_NEW y son específicos de las versiones de SAP.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-108">The steps provided here are for ZQUERY_TST_NEW query and are specific to SAP versions.</span></span>  
  
1. <span data-ttu-id="f6fdf-109">Ejecute la transacción SQ01.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-109">Run the transaction SQ01.</span></span>  
  
2. <span data-ttu-id="f6fdf-110">En el **consulta desde el grupo de usuarios** página, haga clic en **Quick Viewer**.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-110">In the **Query from User Group** page, click **Quick Viewer**.</span></span>  
  
3. <span data-ttu-id="f6fdf-111">En el **Quick Viewer** página, en el **vista rápida** cuadro de texto, escriba `ZQUERY_TST_NEW`y, a continuación, haga clic en **mostrar**.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-111">In the **Quick Viewer** page, in the **Quick View** text box, type `ZQUERY_TST_NEW`, and then click **Display**.</span></span>  
  
4. <span data-ttu-id="f6fdf-112">En el **Quick Viewer** página, haga clic en el **campos de selección** tab para enumerar todos los parámetros en la consulta.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-112">In the **Quick Viewer** page, click the **Selection fields** tab to list all the parameters in the query.</span></span>  
  
    <span data-ttu-id="f6fdf-113">La siguiente ilustración muestra todos los parámetros en la definición de consulta.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-113">The following figure shows all the parameters in the query definition.</span></span>  
  
    <span data-ttu-id="f6fdf-114">![Lista de parámetros para una consulta SAP](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")</span><span class="sxs-lookup"><span data-stu-id="f6fdf-114">![List of parameters for an SAP query](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")</span></span>  
  
5. <span data-ttu-id="f6fdf-115">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-115">Click **Execute**.</span></span> <span data-ttu-id="f6fdf-116">Se muestra la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-116">The following page is displayed.</span></span>  
  
    <span data-ttu-id="f6fdf-117">![Proporcionar valores de parámetro para una consulta SAP](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")</span><span class="sxs-lookup"><span data-stu-id="f6fdf-117">![Provide parameter values for an SAP query](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")</span></span>  
  
6. <span data-ttu-id="f6fdf-118">Haga clic en las flechas de color amarillas para definir cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-118">Click the yellow arrows to define each parameter.</span></span> <span data-ttu-id="f6fdf-119">Puede definir valores específicos de permitidos/no-permitido o puede definir un intervalo de valores permitido/no-permitido.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-119">You can either define specific allowable/non-allowable values or you can define a range of allowable/non-allowable values.</span></span>  <span data-ttu-id="f6fdf-120">Debe especificarse la sintaxis EXECQUERY según los valores configurados en la GUI de SAP para cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-120">The EXECQUERY syntax must be specified based on the values configured in the SAP GUI for each parameter.</span></span>  
  
   <span data-ttu-id="f6fdf-121">La siguiente sección proporciona una explicación sobre cómo se definen los valores en la GUI de SAP y cómo esos valores se traducen a la sintaxis EXECQUERY.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-121">The next section provides an explanation about how the values are defined in the SAP GUI and how those values translate to EXECQUERY syntax.</span></span>  
  
## <a name="frame-an-execquery-syntax"></a><span data-ttu-id="f6fdf-122">Marco de una sintaxis EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="f6fdf-122">Frame an EXECQUERY Syntax</span></span>  
 <span data-ttu-id="f6fdf-123">Echemos un vistazo a lo que la sintaxis EXECQUERY aspecto según los valores de parámetro definidos en la definición de consulta.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-123">Let’s look at what the EXECQUERY syntax looks like based on the parameter values defined in the query definition.</span></span> <span data-ttu-id="f6fdf-124">Para comprender esto, mostraremos algunos ejemplos de cómo configuran los valores para el primer parámetro, **número de dos dígitos**, se traducen en el **ZQUERY_TST_NEW** consulta.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-124">To understand this, we’ll show examples of how the values configured for the first parameter, **Two digit number**, translate to the  **ZQUERY_TST_NEW** query.</span></span>  
  
 <span data-ttu-id="f6fdf-125">En primer lugar, supongamos que los valores de la **único vals** ficha (con un punto verde) se definen como se muestra en la captura de pantalla siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6fdf-125">First, let’s assume the values in the **Single vals** tab (with a green dot) are defined as shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="f6fdf-126">![Lista de valores de parámetro que una consulta puede tener](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")</span><span class="sxs-lookup"><span data-stu-id="f6fdf-126">![List of parameter values that a query can take](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6fdf-127">Este cuadro de diálogo aparece al hacer clic en la flecha amarilla en el **número de dos dígitos** parámetro.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-127">This dialog box appears after you click the yellow arrow against the **Two digit number** parameter.</span></span>  
  
 <span data-ttu-id="f6fdf-128">En tal caso, la sintaxis EXECQUERY es similar:</span><span class="sxs-lookup"><span data-stu-id="f6fdf-128">In such a case, the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5'  
```  
  
 <span data-ttu-id="f6fdf-129">Para la misma consulta, además de los valores en el **único vals** ficha (con un punto verde), también puede tener los valores en el **único vals** ficha (con un punto rojo) se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="f6fdf-129">For the same query, in addition to the values in the **Single vals** tab (with a green dot), you can also have the values in the **Single vals** tab (with a red dot) defined as following:</span></span>  
  
 <span data-ttu-id="f6fdf-130">![Lista de valores de parámetro que no puede tener una consulta](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")</span><span class="sxs-lookup"><span data-stu-id="f6fdf-130">![List of parameter values that a query cannot take](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")</span></span>  
  
 <span data-ttu-id="f6fdf-131">En tal caso, la sintaxis de EXECQUERY es similar:</span><span class="sxs-lookup"><span data-stu-id="f6fdf-131">In such a case, EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8'  
```  
  
 <span data-ttu-id="f6fdf-132">Ahora, si agrega valores a la **intervalos** pestaña (con un punto verde), como se muestra en la captura de pantalla siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6fdf-132">Now, if you add values to the **Ranges** tab (with a green dot), like shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="f6fdf-133">![Intervalo de valores de parámetro que una consulta puede tener](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")</span><span class="sxs-lookup"><span data-stu-id="f6fdf-133">![Range of parameter values that a query can take](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")</span></span>  
  
 <span data-ttu-id="f6fdf-134">la sintaxis EXECQUERY tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="f6fdf-134">the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5'  
```  
  
 <span data-ttu-id="f6fdf-135">De forma similar, si agrega valores a la **intervalos** pestaña (con un punto rojo), como se muestra en la captura de pantalla siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6fdf-135">Similarly, if you add values to the **Ranges** tab (with a red dot), like shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="f6fdf-136">![Intervalo de valores de parámetro que no puede tener una consulta](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")</span><span class="sxs-lookup"><span data-stu-id="f6fdf-136">![Range of parameter values that a query cannot take](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")</span></span>  
  
 <span data-ttu-id="f6fdf-137">la sintaxis EXECQUERY tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="f6fdf-137">the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5', NOT @P1 BETWEEN '6' AND '8'  
```  
  
 <span data-ttu-id="f6fdf-138">Por simplicidad y la descripción, en este tema solo se habla el primer parámetro, **número de dos dígitos**.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-138">For simplicity and understanding, this topic only talks about the first parameter, **Two digit number**.</span></span> <span data-ttu-id="f6fdf-139">Puede usar métodos similares para determinar cómo se traducen los valores definidos para otros parámetros en una sintaxis EXECQUERY.</span><span class="sxs-lookup"><span data-stu-id="f6fdf-139">You can use similar methods to determine how values defined for other parameters translate into an EXECQUERY syntax.</span></span>  
  
