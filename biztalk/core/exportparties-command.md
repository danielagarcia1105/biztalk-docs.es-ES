---
title: Comando ExportParties | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b421c8ed-d505-48ba-9d1d-8519c9d51750
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca525872ccc1cd941673189c4ac176fc4631f22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245820"
---
# <a name="exportparties-command"></a><span data-ttu-id="8154b-102">Comando ExportParties</span><span class="sxs-lookup"><span data-stu-id="8154b-102">ExportParties Command</span></span>
<span data-ttu-id="8154b-103">Exporta todas las entidades y los contratos a un archivo de enlaces XML.</span><span class="sxs-lookup"><span data-stu-id="8154b-103">Exports all the parties and agreements to an XML bindings file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8154b-104">Este comando es nuevo a partir de  **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** y las versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="8154b-104">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>

## <a name="usage"></a><span data-ttu-id="8154b-105">Uso</span><span class="sxs-lookup"><span data-stu-id="8154b-105">Usage</span></span>
  <span data-ttu-id="8154b-106">**BTSTask ExportParties-destino**:*valor* [**-Server**:*valor*] [**-base de datos**: *valor*]</span><span class="sxs-lookup"><span data-stu-id="8154b-106">**BTSTask ExportParties -Destination**:*value* [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8154b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8154b-107">Parameters</span></span>

|<span data-ttu-id="8154b-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="8154b-108">Parameter</span></span>|<span data-ttu-id="8154b-109">Necesario</span><span class="sxs-lookup"><span data-stu-id="8154b-109">Required</span></span>|<span data-ttu-id="8154b-110">Valor</span><span class="sxs-lookup"><span data-stu-id="8154b-110">Value</span></span>|  
|---|---|---|  
| <span data-ttu-id="8154b-111">**: Destino**</span><span class="sxs-lookup"><span data-stu-id="8154b-111">**-Destination**</span></span> | <span data-ttu-id="8154b-112">Necesario</span><span class="sxs-lookup"><span data-stu-id="8154b-112">Required</span></span> | <span data-ttu-id="8154b-113">Ruta de acceso y el nombre del archivo de enlace XML que se escribirá.</span><span class="sxs-lookup"><span data-stu-id="8154b-113">Path and file name of the XML binding file to write.</span></span> |
| <span data-ttu-id="8154b-114">**-Servidor**</span><span class="sxs-lookup"><span data-stu-id="8154b-114">**-Server**</span></span> | <span data-ttu-id="8154b-115">Opcional</span><span class="sxs-lookup"><span data-stu-id="8154b-115">Optional</span></span> | <span data-ttu-id="8154b-116">El nombre de SQL server que hospeda la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8154b-116">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="8154b-117">**-Base de datos**</span><span class="sxs-lookup"><span data-stu-id="8154b-117">**-Database**</span></span> | <span data-ttu-id="8154b-118">Opcional</span><span class="sxs-lookup"><span data-stu-id="8154b-118">Optional</span></span> | <span data-ttu-id="8154b-119">Nombre de la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8154b-119">The name of the BizTalk configuration database.</span></span>|

## <a name="sample"></a><span data-ttu-id="8154b-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8154b-120">Sample</span></span>
  `ExportParties  -Destination:"C:\Temp\MyParties.Xml"` 

## <a name="remarks"></a><span data-ttu-id="8154b-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8154b-121">Remarks</span></span>
  <span data-ttu-id="8154b-122">Se exporta solo entidades, acuerdos y configuración de reserva de EDI.</span><span class="sxs-lookup"><span data-stu-id="8154b-122">Only parties, agreements, and EDI fallback settings are exported.</span></span> <span data-ttu-id="8154b-123">No hay artefactos de la aplicación se exportan.</span><span class="sxs-lookup"><span data-stu-id="8154b-123">No application artifacts are exported.</span></span>
