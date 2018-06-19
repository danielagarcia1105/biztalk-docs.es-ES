---
title: Solucionar problemas relacionados con el proveedor de datos para Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, troubleshooting
- troubleshooting, Data Provider for Siebel
ms.assetid: 2bfe69a2-d6de-466d-9f36-f11c386c771c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6e100635b1cb2db5c78ff713c8e6ad32d4e7d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222004"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-siebel"></a><span data-ttu-id="0769c-102">Solucionar problemas relacionados con el proveedor de datos para Siebel</span><span class="sxs-lookup"><span data-stu-id="0769c-102">Troubleshoot Issues with the Data Provider for Siebel</span></span>
<span data-ttu-id="0769c-103">Esta sección describe el uso de técnicas de solución de problemas para resolver los errores que pueden surgir al usar el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="0769c-103">This section discusses using troubleshooting techniques to resolve errors that you might encounter when using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="0769c-104">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="0769c-104">Known Issues</span></span>  
  
### <a name="data-provider-for-siebel-may-give-component-datareader-source-380-error"></a><span data-ttu-id="0769c-105">Proveedor de datos para Siebel puede provocar el error de "componente"DataReader, origen' (380)"</span><span class="sxs-lookup"><span data-stu-id="0769c-105">Data Provider for Siebel may give "component 'DataReader Source' (380)" error</span></span>  
 <span data-ttu-id="0769c-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="0769c-106">**Problem**</span></span>  
  
 <span data-ttu-id="0769c-107">Al realizar una consulta SELECT en un componente de negocio de Siebel, el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] puede provocar un error de "componente"DataReader, origen' (380)".</span><span class="sxs-lookup"><span data-stu-id="0769c-107">While performing a SELECT query on a Siebel business component, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] may give a "component 'DataReader Source' (380)" error.</span></span>  
  
 <span data-ttu-id="0769c-108">**Causa**</span><span class="sxs-lookup"><span data-stu-id="0769c-108">**Cause**</span></span>  
  
 <span data-ttu-id="0769c-109">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] da como resultado de este error si el valor recibido desde el sistema Siebel para un parámetro supera la propiedad maxLength para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="0769c-109">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] gives this error if the value received from the Siebel system for a parameter exceeds the maxLength property for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0769c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0769c-110">See Also</span></span>  
[<span data-ttu-id="0769c-111">Solucionar problemas del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="0769c-111">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)