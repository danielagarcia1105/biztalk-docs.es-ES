---
title: ImportParties (comando) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d43e2c-401c-4450-ad9b-2528086b99e4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c25b913b6479b857fb7cee4aec10e6984f2195
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998541"
---
# <a name="importparties-command"></a><span data-ttu-id="e3644-102">ImportParties (comando)</span><span class="sxs-lookup"><span data-stu-id="e3644-102">ImportParties Command</span></span>
<span data-ttu-id="e3644-103">Importa las entidades de negocio a negocio y los contratos desde un archivo de enlace XML de origen en la base de datos de configuración, sin incluir ningún artefacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e3644-103">Imports the business-to-business parties and agreements from a source XML binding file in the configuration database, without importing any of the application artifacts.</span></span> <span data-ttu-id="e3644-104">Para obtener más información, consulte **comentarios** en este tema.</span><span class="sxs-lookup"><span data-stu-id="e3644-104">For more information, see **Remarks** in this topic.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="e3644-105">Este comando es nuevo a partir de **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** y las versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="e3644-105">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>
> 
> [!NOTE]
>  <span data-ttu-id="e3644-106">Enlace los archivos generados en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no tiene una aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="e3644-106">Binding files generated in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have an application specified.</span></span> <span data-ttu-id="e3644-107">Se importan a la aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e3644-107">They are imported into the default application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="e3644-108">Uso</span><span class="sxs-lookup"><span data-stu-id="e3644-108">Usage</span></span>  
  <span data-ttu-id="e3644-109">**BTSTask ImportParties-origen**:*valor* [**- ExcludeEdiFallbackSettings**] [**-Server**:*valor*] [**-Base de datos**:*valor*]</span><span class="sxs-lookup"><span data-stu-id="e3644-109">**BTSTask ImportParties -Source**:*value* [**-ExcludeEdiFallbackSettings**] [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="e3644-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3644-110">Parameters</span></span>  
  
|<span data-ttu-id="e3644-111">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e3644-111">Parameter</span></span>|<span data-ttu-id="e3644-112">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e3644-112">Required</span></span>|<span data-ttu-id="e3644-113">Valor</span><span class="sxs-lookup"><span data-stu-id="e3644-113">Value</span></span>|  
|---|---|---|  
|<span data-ttu-id="e3644-114">**: Origen**</span><span class="sxs-lookup"><span data-stu-id="e3644-114">**-Source**</span></span> | <span data-ttu-id="e3644-115">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e3644-115">Required</span></span> | <span data-ttu-id="e3644-116">La ruta de acceso y el nombre del archivo de enlace XML para leer.</span><span class="sxs-lookup"><span data-stu-id="e3644-116">The path and file name of the XML binding file to read.</span></span>|
|<span data-ttu-id="e3644-117">**-ExcludeEdiFallbackSettings**</span><span class="sxs-lookup"><span data-stu-id="e3644-117">**-ExcludeEdiFallbackSettings**</span></span> | <span data-ttu-id="e3644-118">Opcional</span><span class="sxs-lookup"><span data-stu-id="e3644-118">Optional</span></span> | <span data-ttu-id="e3644-119">Si se especifica, excluye la configuración de (x12 y edifact) reserva edi desde el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="e3644-119">If specified, it excludes edi fallback (x12 and edifact) settings from the binding file.</span></span>  |
| <span data-ttu-id="e3644-120">**-Servidor**</span><span class="sxs-lookup"><span data-stu-id="e3644-120">**-Server**</span></span> | <span data-ttu-id="e3644-121">Opcional</span><span class="sxs-lookup"><span data-stu-id="e3644-121">Optional</span></span> | <span data-ttu-id="e3644-122">El nombre de SQL server que hospeda la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e3644-122">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="e3644-123">**-Base de datos**</span><span class="sxs-lookup"><span data-stu-id="e3644-123">**-Database**</span></span> | <span data-ttu-id="e3644-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="e3644-124">Optional</span></span> | <span data-ttu-id="e3644-125">Nombre de la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e3644-125">The name of the BizTalk configuration database.</span></span> |

## <a name="sample"></a><span data-ttu-id="e3644-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3644-126">Sample</span></span>
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a><span data-ttu-id="e3644-127">Notas</span><span class="sxs-lookup"><span data-stu-id="e3644-127">Remarks</span></span>
<span data-ttu-id="e3644-128">Si el archivo de enlace también tiene artefactos de la aplicación, a continuación, no se importan.</span><span class="sxs-lookup"><span data-stu-id="e3644-128">If the binding file also has application artifacts, then they are not imported.</span></span> <span data-ttu-id="e3644-129">Se importan solo entidades y acuerdos.</span><span class="sxs-lookup"><span data-stu-id="e3644-129">Only parties and agreements are imported.</span></span>