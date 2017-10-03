---
title: Comando ImportSettings | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 587f7e1f-9cf7-4e7b-90cd-11a266f474dc
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c609634422f8c8b5f2c1a96691fe4eda708e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importsettings-command"></a><span data-ttu-id="96295-102">Comando ImportSettings</span><span class="sxs-lookup"><span data-stu-id="96295-102">ImportSettings Command</span></span>
<span data-ttu-id="96295-103">Importa la configuración de grupo, host o instancia de host de BizTalk desde un archivo XML de origen a la base de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="96295-103">Imports the BizTalk group, host, or host instance settings from a source XML file to the configuration database.</span></span> <span data-ttu-id="96295-104">La configuración se asigna tal como está en el archivo XML de asignación.</span><span class="sxs-lookup"><span data-stu-id="96295-104">The settings are mapped as they are in the mapping XML file.</span></span> <span data-ttu-id="96295-105">Estas opciones se pueden haber exportado tal y como se describe en [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) o [importación o exportación BTSTask de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-btstask.md).</span><span class="sxs-lookup"><span data-stu-id="96295-105">These settings may have been exported as described in [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) or [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="96295-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="96295-106">Prerequisites</span></span>  
 <span data-ttu-id="96295-107">Para realizar esta operación, debe iniciar sesión como miembro del grupo Administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="96295-107">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="96295-108">Uso</span><span class="sxs-lookup"><span data-stu-id="96295-108">Usage</span></span>  
 `ImportSettings –Source:value –Map: value [-Server:value] [-Database:value]`  
  
## <a name="parameters"></a><span data-ttu-id="96295-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96295-109">Parameters</span></span>  
  
|<span data-ttu-id="96295-110">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="96295-110">**Parameter**</span></span>|<span data-ttu-id="96295-111">Necesario</span><span class="sxs-lookup"><span data-stu-id="96295-111">Required</span></span>|<span data-ttu-id="96295-112">Valor</span><span class="sxs-lookup"><span data-stu-id="96295-112">Value</span></span>|  
|-------------------|--------------|-----------|  
|<span data-ttu-id="96295-113">**-Origen**</span><span class="sxs-lookup"><span data-stu-id="96295-113">**-Source**</span></span>|<span data-ttu-id="96295-114">Sí</span><span class="sxs-lookup"><span data-stu-id="96295-114">Yes</span></span>|<span data-ttu-id="96295-115">Ruta de acceso y el nombre del archivo XML de configuración exportado.</span><span class="sxs-lookup"><span data-stu-id="96295-115">Path and file name of the exported settings XML file.</span></span>|  
|<span data-ttu-id="96295-116">**-Mapa**</span><span class="sxs-lookup"><span data-stu-id="96295-116">**-Map**</span></span>|<span data-ttu-id="96295-117">Sí</span><span class="sxs-lookup"><span data-stu-id="96295-117">Yes</span></span>|<span data-ttu-id="96295-118">Ruta de acceso y el nombre del archivo XML de asignación.</span><span class="sxs-lookup"><span data-stu-id="96295-118">Path and file name of the mapping XML file.</span></span>|  
|<span data-ttu-id="96295-119">**-Servidor**</span><span class="sxs-lookup"><span data-stu-id="96295-119">**-Server**</span></span>|<span data-ttu-id="96295-120">Opcional</span><span class="sxs-lookup"><span data-stu-id="96295-120">Optional</span></span>|<span data-ttu-id="96295-121">El nombre del equipo SQL Server que hospeda la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="96295-121">The name of SQL Server computer hosting the BizTalk configuration database.</span></span>|  
|<span data-ttu-id="96295-122">**-Base de datos**</span><span class="sxs-lookup"><span data-stu-id="96295-122">**-Database**</span></span>|<span data-ttu-id="96295-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="96295-123">Optional</span></span>|<span data-ttu-id="96295-124">Nombre de la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="96295-124">The name of the BizTalk configuration database.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="96295-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96295-125">Sample</span></span>  
 `BTSTask ImportSettings /Source:”C:\My Folder>\ExportedSettings.xml” /Map:Mappings.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a><span data-ttu-id="96295-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96295-126">Remarks</span></span>  
 <span data-ttu-id="96295-127">Los parámetros no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="96295-127">Parameters are not case-sensitive.</span></span> <span data-ttu-id="96295-128">No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="96295-128">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96295-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="96295-129">See Also</span></span>  
 [<span data-ttu-id="96295-130">Referencia de línea de comandos de BTSTask</span><span class="sxs-lookup"><span data-stu-id="96295-130">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)