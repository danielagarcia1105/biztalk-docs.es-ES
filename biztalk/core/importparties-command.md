---
title: Comando ImportParties | Documentos de Microsoft
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
ms.openlocfilehash: 15edad97134d3dbccc6f4b1af9395cb0bc01febd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257012"
---
# <a name="importparties-command"></a><span data-ttu-id="6d1ff-102">Comando ImportParties</span><span class="sxs-lookup"><span data-stu-id="6d1ff-102">ImportParties Command</span></span>
<span data-ttu-id="6d1ff-103">Importa las entidades de negocio a negocio y contratos desde un archivo de enlace XML de origen en la base de datos de configuración, sin importar cualquiera de los artefactos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-103">Imports the business-to-business parties and agreements from a source XML binding file in the configuration database, without importing any of the application artifacts.</span></span> <span data-ttu-id="6d1ff-104">Para obtener más información, consulte **comentarios** en este tema.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-104">For more information, see **Remarks** in this topic.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="6d1ff-105">Este comando es nuevo a partir de  **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** y las versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-105">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="6d1ff-106">Enlace de archivos que se generan en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no tiene una aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-106">Binding files generated in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have an application specified.</span></span> <span data-ttu-id="6d1ff-107">Se importan a la aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-107">They are imported into the default application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="6d1ff-108">Uso</span><span class="sxs-lookup"><span data-stu-id="6d1ff-108">Usage</span></span>  
  <span data-ttu-id="6d1ff-109">**BTSTask ImportParties-origen**:*valor* [**- ExcludeEdiFallbackSettings**] [**-Server**:*valor*] [**-Base de datos**:*valor*]</span><span class="sxs-lookup"><span data-stu-id="6d1ff-109">**BTSTask ImportParties -Source**:*value* [**-ExcludeEdiFallbackSettings**] [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="6d1ff-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d1ff-110">Parameters</span></span>  
  
|<span data-ttu-id="6d1ff-111">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6d1ff-111">Parameter</span></span>|<span data-ttu-id="6d1ff-112">Necesario</span><span class="sxs-lookup"><span data-stu-id="6d1ff-112">Required</span></span>|<span data-ttu-id="6d1ff-113">Valor</span><span class="sxs-lookup"><span data-stu-id="6d1ff-113">Value</span></span>|  
|---|---|---|  
|<span data-ttu-id="6d1ff-114">**-Origen**</span><span class="sxs-lookup"><span data-stu-id="6d1ff-114">**-Source**</span></span> | <span data-ttu-id="6d1ff-115">Necesario</span><span class="sxs-lookup"><span data-stu-id="6d1ff-115">Required</span></span> | <span data-ttu-id="6d1ff-116">La ruta de acceso y el nombre del archivo de enlace XML para leer.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-116">The path and file name of the XML binding file to read.</span></span>|
|<span data-ttu-id="6d1ff-117">**-ExcludeEdiFallbackSettings**</span><span class="sxs-lookup"><span data-stu-id="6d1ff-117">**-ExcludeEdiFallbackSettings**</span></span> | <span data-ttu-id="6d1ff-118">Opcional</span><span class="sxs-lookup"><span data-stu-id="6d1ff-118">Optional</span></span> | <span data-ttu-id="6d1ff-119">Si se especifica, excluye la configuración de (x12 y edifact) reserva edi desde el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-119">If specified, it excludes edi fallback (x12 and edifact) settings from the binding file.</span></span>  |
| <span data-ttu-id="6d1ff-120">**-Servidor**</span><span class="sxs-lookup"><span data-stu-id="6d1ff-120">**-Server**</span></span> | <span data-ttu-id="6d1ff-121">Opcional</span><span class="sxs-lookup"><span data-stu-id="6d1ff-121">Optional</span></span> | <span data-ttu-id="6d1ff-122">El nombre de SQL server que hospeda la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-122">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="6d1ff-123">**-Base de datos**</span><span class="sxs-lookup"><span data-stu-id="6d1ff-123">**-Database**</span></span> | <span data-ttu-id="6d1ff-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="6d1ff-124">Optional</span></span> | <span data-ttu-id="6d1ff-125">Nombre de la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-125">The name of the BizTalk configuration database.</span></span> |

## <a name="sample"></a><span data-ttu-id="6d1ff-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d1ff-126">Sample</span></span>
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a><span data-ttu-id="6d1ff-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d1ff-127">Remarks</span></span>
<span data-ttu-id="6d1ff-128">Si el archivo de enlace también tiene los artefactos de la aplicación, a continuación, no se importan.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-128">If the binding file also has application artifacts, then they are not imported.</span></span> <span data-ttu-id="6d1ff-129">Se importan solo entidades y acuerdos.</span><span class="sxs-lookup"><span data-stu-id="6d1ff-129">Only parties and agreements are imported.</span></span>