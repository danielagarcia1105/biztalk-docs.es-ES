---
title: Comando ExportSettings | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa34dab1-c854-473e-a693-43ba45624e16
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab8c39ef6903affbd2a1446bbde18a56e1a7778c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245948"
---
# <a name="exportsettings-command"></a><span data-ttu-id="f6d47-102">Comando ExportSettings</span><span class="sxs-lookup"><span data-stu-id="f6d47-102">ExportSettings Command</span></span>
<span data-ttu-id="f6d47-103">El comando ExportSettings permite exportar la configuración de BizTalk Server de la base de datos de configuración de BizTalk Server a un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="f6d47-103">The ExportSettings command nables you to export the BizTalk Server settings from a BizTalk Server configuration database to an XML file.</span></span> <span data-ttu-id="f6d47-104">A continuación, puede importar esta configuración en otro entorno tal como se describe en [cómo importar configuración de BizTalk utilizando el panel de configuración](../core/how-to-import-biztalk-settings-using-settings-dashboard.md) o [cómo importar la configuración de BizTalk usando BTSTask](../core/how-to-import-biztalk-settings-using-btstask.md).</span><span class="sxs-lookup"><span data-stu-id="f6d47-104">You can then import these settings in another environment as described in [How to Import BizTalk Settings Using Settings Dashboard](../core/how-to-import-biztalk-settings-using-settings-dashboard.md) or [How to Import BizTalk Settings Using BTSTask](../core/how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f6d47-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f6d47-105">Prerequisites</span></span>  
 <span data-ttu-id="f6d47-106">Para realizar esta operación, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f6d47-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="f6d47-107">Uso</span><span class="sxs-lookup"><span data-stu-id="f6d47-107">Usage</span></span>  
 `ExportSettings –Destination:value[-Server:value] [-Database:value]`  
  
## <a name="parameters"></a><span data-ttu-id="f6d47-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6d47-108">Parameters</span></span>  
  
|<span data-ttu-id="f6d47-109">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="f6d47-109">**Parameter**</span></span>|<span data-ttu-id="f6d47-110">Necesario</span><span class="sxs-lookup"><span data-stu-id="f6d47-110">Required</span></span>|<span data-ttu-id="f6d47-111">Valor</span><span class="sxs-lookup"><span data-stu-id="f6d47-111">Value</span></span>|  
|-------------------|--------------|-----------|  
|<span data-ttu-id="f6d47-112">**: Destino**</span><span class="sxs-lookup"><span data-stu-id="f6d47-112">**-Destination**</span></span>|<span data-ttu-id="f6d47-113">Sí</span><span class="sxs-lookup"><span data-stu-id="f6d47-113">Yes</span></span>|<span data-ttu-id="f6d47-114">Ruta de acceso y nombre de archivo del archivo XML que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="f6d47-114">Path and file name of the XML file to write.</span></span>|  
|<span data-ttu-id="f6d47-115">**-Servidor**</span><span class="sxs-lookup"><span data-stu-id="f6d47-115">**-Server**</span></span>|<span data-ttu-id="f6d47-116">Opcional</span><span class="sxs-lookup"><span data-stu-id="f6d47-116">Optional</span></span>|<span data-ttu-id="f6d47-117">Nombre del SQL Server que hospeda la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f6d47-117">The name of SQL Server hosting the BizTalk configuration database.</span></span>|  
|<span data-ttu-id="f6d47-118">**-Base de datos**</span><span class="sxs-lookup"><span data-stu-id="f6d47-118">**-Database**</span></span>|<span data-ttu-id="f6d47-119">Opcional</span><span class="sxs-lookup"><span data-stu-id="f6d47-119">Optional</span></span>|<span data-ttu-id="f6d47-120">Nombre de la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f6d47-120">The name of the BizTalk configuration database.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="f6d47-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6d47-121">Sample</span></span>  
 `BTSTask ExportSettings /Destination:MyFile.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a><span data-ttu-id="f6d47-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6d47-122">Remarks</span></span>  
 <span data-ttu-id="f6d47-123">Los parámetros no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f6d47-123">Parameters are not case-sensitive.</span></span> <span data-ttu-id="f6d47-124">No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="f6d47-124">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d47-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6d47-125">See Also</span></span>  
 [<span data-ttu-id="f6d47-126">Referencia de línea de comandos de BTSTask</span><span class="sxs-lookup"><span data-stu-id="f6d47-126">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)