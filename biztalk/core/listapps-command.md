---
title: ListApps (comando) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5eb0af-e153-4639-a6c0-56c951827c7c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0206471feefe8ffe52ec2045ede865bb064ea452
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974013"
---
# <a name="listapps-command"></a><span data-ttu-id="e6d56-102">ListApps (comando)</span><span class="sxs-lookup"><span data-stu-id="e6d56-102">ListApps Command</span></span>
<span data-ttu-id="e6d56-103">Imprime en la consola el nombre y la descripción de todas las aplicaciones de BizTalk de la base de datos de administración de BizTalk especificada.</span><span class="sxs-lookup"><span data-stu-id="e6d56-103">Prints to the console the name and description of all of the BizTalk applications in the specified BizTalk Management database.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="e6d56-104">Uso</span><span class="sxs-lookup"><span data-stu-id="e6d56-104">Usage</span></span>  
 <span data-ttu-id="e6d56-105">**BTSTask ListApps** [**/Server:**<em>valor</em>] [**/Database:**<em>valor</em>]</span><span class="sxs-lookup"><span data-stu-id="e6d56-105">**BTSTask ListApps** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="e6d56-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6d56-106">Parameters</span></span>  
  
|<span data-ttu-id="e6d56-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e6d56-107">Parameter</span></span>|<span data-ttu-id="e6d56-108">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e6d56-108">Required</span></span>|<span data-ttu-id="e6d56-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6d56-109">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="e6d56-110">**/ Servidor** (o **/S**, vea la sección Comentarios)</span><span class="sxs-lookup"><span data-stu-id="e6d56-110">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="e6d56-111">no</span><span class="sxs-lookup"><span data-stu-id="e6d56-111">No</span></span>|<span data-ttu-id="e6d56-112">Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.</span><span class="sxs-lookup"><span data-stu-id="e6d56-112">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="e6d56-113">Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="e6d56-113">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="e6d56-114">Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)</span><span class="sxs-lookup"><span data-stu-id="e6d56-114">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="e6d56-115">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="e6d56-115">Examples:</span></span><br /><br /> <span data-ttu-id="e6d56-116">Servidor = MyServer</span><span class="sxs-lookup"><span data-stu-id="e6d56-116">Server=MyServer</span></span><br /><br /> <span data-ttu-id="e6d56-117">Servidor = MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="e6d56-117">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="e6d56-118">Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="e6d56-118">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="e6d56-119">**/ Base de datos** (o **/D**, vea la sección Comentarios)</span><span class="sxs-lookup"><span data-stu-id="e6d56-119">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="e6d56-120">no</span><span class="sxs-lookup"><span data-stu-id="e6d56-120">No</span></span>|<span data-ttu-id="e6d56-121">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e6d56-121">Name of the BizTalk Management database.</span></span> <span data-ttu-id="e6d56-122">Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6d56-122">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="e6d56-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6d56-123">Sample</span></span>  
 <span data-ttu-id="e6d56-124">**BTSTask ListApps**</span><span class="sxs-lookup"><span data-stu-id="e6d56-124">**BTSTask ListApps**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6d56-125">Notas</span><span class="sxs-lookup"><span data-stu-id="e6d56-125">Remarks</span></span>  
 <span data-ttu-id="e6d56-126">Los parámetros no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e6d56-126">Parameters are not case-sensitive.</span></span> <span data-ttu-id="e6d56-127">No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="e6d56-127">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d56-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6d56-128">See Also</span></span>  
 [<span data-ttu-id="e6d56-129">Referencia de línea de comandos de BTSTask</span><span class="sxs-lookup"><span data-stu-id="e6d56-129">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)