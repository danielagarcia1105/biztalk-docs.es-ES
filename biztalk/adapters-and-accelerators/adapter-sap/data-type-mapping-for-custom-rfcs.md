---
title: Tipo de datos de asignación para las solicitudes de cambio personalizadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom RFCs, data type mapping
ms.assetid: 33539a5a-bdfc-423f-8026-436f69a20c70
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cac254734a35658e3aa635b086f765e8f06494a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-mapping-for-custom-rfcs"></a><span data-ttu-id="8a1f2-102">Asignación de tipos de datos para las solicitudes de cambio personalizadas</span><span class="sxs-lookup"><span data-stu-id="8a1f2-102">Data Type Mapping for Custom RFCs</span></span>
<span data-ttu-id="8a1f2-103">En la tabla siguiente proporciona información sobre los tipos de datos SAP y cómo se asignan a tipos de datos de .NET para la solicitud de cambio de Z_EXTRACT_DATA_OO.</span><span class="sxs-lookup"><span data-stu-id="8a1f2-103">The following table provides information about SAP data types and how they are mapped to .NET data types for the Z_EXTRACT_DATA_OO RFC.</span></span> <span data-ttu-id="8a1f2-104">Este RFC personalizada se usa por la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a1f2-104">This custom RFC is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a1f2-105">Caso Z_EXECUTE_SAP_QUERY, que se utiliza en el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] para ejecutar el comando EXECQUERY, todos los tipos de datos SAP se convierten en tipos de cadena. NET.</span><span class="sxs-lookup"><span data-stu-id="8a1f2-105">For the Z_EXECUTE_SAP_QUERY, which is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] to execute the EXECQUERY command, all SAP data types are converted to .NET string types.</span></span>  
  
|<span data-ttu-id="8a1f2-106">Tipo de datos SAP</span><span class="sxs-lookup"><span data-stu-id="8a1f2-106">SAP Data Type</span></span>|<span data-ttu-id="8a1f2-107">Tipo de datos de .NET</span><span class="sxs-lookup"><span data-stu-id="8a1f2-107">.NET Data Type</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="8a1f2-108">ACCP</span><span class="sxs-lookup"><span data-stu-id="8a1f2-108">ACCP</span></span>|<span data-ttu-id="8a1f2-109">-Int32</span><span class="sxs-lookup"><span data-stu-id="8a1f2-109">-   Int32</span></span><br /><span data-ttu-id="8a1f2-110">-Cadena, si **disabledatavalidation** opción está establecida en la instrucción SELECT o EXEC.</span><span class="sxs-lookup"><span data-stu-id="8a1f2-110">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="8a1f2-111">CHAR</span><span class="sxs-lookup"><span data-stu-id="8a1f2-111">CHAR</span></span>|<span data-ttu-id="8a1f2-112">String</span><span class="sxs-lookup"><span data-stu-id="8a1f2-112">String</span></span>|  
|<span data-ttu-id="8a1f2-113">CLNT</span><span class="sxs-lookup"><span data-stu-id="8a1f2-113">CLNT</span></span>|<span data-ttu-id="8a1f2-114">String</span><span class="sxs-lookup"><span data-stu-id="8a1f2-114">String</span></span>|  
|<span data-ttu-id="8a1f2-115">CUKY</span><span class="sxs-lookup"><span data-stu-id="8a1f2-115">CUKY</span></span>|<span data-ttu-id="8a1f2-116">String</span><span class="sxs-lookup"><span data-stu-id="8a1f2-116">String</span></span>|  
|<span data-ttu-id="8a1f2-117">DIV</span><span class="sxs-lookup"><span data-stu-id="8a1f2-117">CURR</span></span>|<span data-ttu-id="8a1f2-118">Decimal, si una precisión menor o igual que 28</span><span class="sxs-lookup"><span data-stu-id="8a1f2-118">Decimal, if precision less than or equal to 28</span></span><br /><br /> <span data-ttu-id="8a1f2-119">Cadena, si precisión superior a 28</span><span class="sxs-lookup"><span data-stu-id="8a1f2-119">String, if precision greater than 28</span></span>|  
|<span data-ttu-id="8a1f2-120">DATS</span><span class="sxs-lookup"><span data-stu-id="8a1f2-120">DATS</span></span>|<span data-ttu-id="8a1f2-121">-Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="8a1f2-121">-   DateTime</span></span><br /><span data-ttu-id="8a1f2-122">-Cadena, si **disabledatavalidation** opción está establecida en la instrucción SELECT o EXEC.</span><span class="sxs-lookup"><span data-stu-id="8a1f2-122">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="8a1f2-123">DEC</span><span class="sxs-lookup"><span data-stu-id="8a1f2-123">DEC</span></span>|<span data-ttu-id="8a1f2-124">Decimal</span><span class="sxs-lookup"><span data-stu-id="8a1f2-124">Decimal</span></span>|  
|<span data-ttu-id="8a1f2-125">FLTP</span><span class="sxs-lookup"><span data-stu-id="8a1f2-125">FLTP</span></span>|<span data-ttu-id="8a1f2-126">Doble</span><span class="sxs-lookup"><span data-stu-id="8a1f2-126">Double</span></span>|  
|<span data-ttu-id="8a1f2-127">INT1</span><span class="sxs-lookup"><span data-stu-id="8a1f2-127">INT1</span></span>|<span data-ttu-id="8a1f2-128">Byte</span><span class="sxs-lookup"><span data-stu-id="8a1f2-128">Byte</span></span>|  
|<span data-ttu-id="8a1f2-129">INT2</span><span class="sxs-lookup"><span data-stu-id="8a1f2-129">INT2</span></span>|<span data-ttu-id="8a1f2-130">Int16</span><span class="sxs-lookup"><span data-stu-id="8a1f2-130">Int16</span></span>|  
|<span data-ttu-id="8a1f2-131">INT4</span><span class="sxs-lookup"><span data-stu-id="8a1f2-131">INT4</span></span>|<span data-ttu-id="8a1f2-132">Int32</span><span class="sxs-lookup"><span data-stu-id="8a1f2-132">Int32</span></span>|  
|<span data-ttu-id="8a1f2-133">LANG</span><span class="sxs-lookup"><span data-stu-id="8a1f2-133">LANG</span></span>|<span data-ttu-id="8a1f2-134">String</span><span class="sxs-lookup"><span data-stu-id="8a1f2-134">String</span></span>|  
|<span data-ttu-id="8a1f2-135">NUMC</span><span class="sxs-lookup"><span data-stu-id="8a1f2-135">NUMC</span></span>|<span data-ttu-id="8a1f2-136">-Int32, si el campo longitud menor o igual a 9</span><span class="sxs-lookup"><span data-stu-id="8a1f2-136">-   Int32, if field length less than or equal to 9</span></span><br /><span data-ttu-id="8a1f2-137">-Int64, si el campo longitud mayor que 9 y menor o igual a 19</span><span class="sxs-lookup"><span data-stu-id="8a1f2-137">-   Int64, if field length greater than 9 and less than or equal to 19</span></span><br /><span data-ttu-id="8a1f2-138">-Cadena, si es mayor que 19</span><span class="sxs-lookup"><span data-stu-id="8a1f2-138">-   String, if greater than 19</span></span><br /><span data-ttu-id="8a1f2-139">-Cadena, si **disabledatavalidation** opción está establecida en la instrucción SELECT o EXEC.</span><span class="sxs-lookup"><span data-stu-id="8a1f2-139">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="8a1f2-140">PREC</span><span class="sxs-lookup"><span data-stu-id="8a1f2-140">PREC</span></span>|<span data-ttu-id="8a1f2-141">Int16</span><span class="sxs-lookup"><span data-stu-id="8a1f2-141">Int16</span></span>|  
|<span data-ttu-id="8a1f2-142">QUAN</span><span class="sxs-lookup"><span data-stu-id="8a1f2-142">QUAN</span></span>|<span data-ttu-id="8a1f2-143">Decimal</span><span class="sxs-lookup"><span data-stu-id="8a1f2-143">Decimal</span></span>|  
|<span data-ttu-id="8a1f2-144">RAW</span><span class="sxs-lookup"><span data-stu-id="8a1f2-144">RAW</span></span>|<span data-ttu-id="8a1f2-145">Byte]</span><span class="sxs-lookup"><span data-stu-id="8a1f2-145">Byte []</span></span>|  
|<span data-ttu-id="8a1f2-146">RSTR</span><span class="sxs-lookup"><span data-stu-id="8a1f2-146">RSTR</span></span>|<span data-ttu-id="8a1f2-147">Byte]</span><span class="sxs-lookup"><span data-stu-id="8a1f2-147">Byte []</span></span>|  
|<span data-ttu-id="8a1f2-148">SSTR</span><span class="sxs-lookup"><span data-stu-id="8a1f2-148">SSTR</span></span>|<span data-ttu-id="8a1f2-149">String</span><span class="sxs-lookup"><span data-stu-id="8a1f2-149">String</span></span>|  
|<span data-ttu-id="8a1f2-150">STRG</span><span class="sxs-lookup"><span data-stu-id="8a1f2-150">STRG</span></span>|<span data-ttu-id="8a1f2-151">String</span><span class="sxs-lookup"><span data-stu-id="8a1f2-151">String</span></span>|  
|<span data-ttu-id="8a1f2-152">TIM</span><span class="sxs-lookup"><span data-stu-id="8a1f2-152">TIMS</span></span>|<span data-ttu-id="8a1f2-153">-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="8a1f2-153">-   TimeSpan</span></span><br /><span data-ttu-id="8a1f2-154">-Cadena, si **disabledatavalidation** opción está establecida en la instrucción SELECT o EXEC.</span><span class="sxs-lookup"><span data-stu-id="8a1f2-154">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="8a1f2-155">UNIDAD</span><span class="sxs-lookup"><span data-stu-id="8a1f2-155">UNIT</span></span>|<span data-ttu-id="8a1f2-156">String</span><span class="sxs-lookup"><span data-stu-id="8a1f2-156">String</span></span>|  
|<span data-ttu-id="8a1f2-157">LCHR</span><span class="sxs-lookup"><span data-stu-id="8a1f2-157">LCHR</span></span>|<span data-ttu-id="8a1f2-158">String</span><span class="sxs-lookup"><span data-stu-id="8a1f2-158">String</span></span>|  
|<span data-ttu-id="8a1f2-159">LRAW</span><span class="sxs-lookup"><span data-stu-id="8a1f2-159">LRAW</span></span>|<span data-ttu-id="8a1f2-160">Byte]</span><span class="sxs-lookup"><span data-stu-id="8a1f2-160">Byte []</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a1f2-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a1f2-161">See Also</span></span>  
 [<span data-ttu-id="8a1f2-162">Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="8a1f2-162">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)