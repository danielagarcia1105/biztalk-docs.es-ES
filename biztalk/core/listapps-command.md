---
title: El comando ListApps | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a5eb0af-e153-4639-a6c0-56c951827c7c
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 785d98655cbe1ef32c00120dc1e54227717ebcae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="listapps-command"></a><span data-ttu-id="49fbf-102">ListApps (comando)</span><span class="sxs-lookup"><span data-stu-id="49fbf-102">ListApps Command</span></span>
<span data-ttu-id="49fbf-103">Imprime en la consola el nombre y la descripción de todas las aplicaciones de BizTalk de la base de datos de administración de BizTalk especificada.</span><span class="sxs-lookup"><span data-stu-id="49fbf-103">Prints to the console the name and description of all of the BizTalk applications in the specified BizTalk Management database.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="49fbf-104">Uso</span><span class="sxs-lookup"><span data-stu-id="49fbf-104">Usage</span></span>  
 <span data-ttu-id="49fbf-105">**BTSTask ListApps** [**/Server:***valor*] [**/Database:***valor*]</span><span class="sxs-lookup"><span data-stu-id="49fbf-105">**BTSTask ListApps** [**/Server:***value*] [**/Database:***value*]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="49fbf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="49fbf-106">Parameters</span></span>  
  
|<span data-ttu-id="49fbf-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="49fbf-107">Parameter</span></span>|<span data-ttu-id="49fbf-108">Necesario</span><span class="sxs-lookup"><span data-stu-id="49fbf-108">Required</span></span>|<span data-ttu-id="49fbf-109">Description</span><span class="sxs-lookup"><span data-stu-id="49fbf-109">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="49fbf-110">**/ Servidor** (o **/S**, vea la sección Comentarios)</span><span class="sxs-lookup"><span data-stu-id="49fbf-110">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="49fbf-111">No</span><span class="sxs-lookup"><span data-stu-id="49fbf-111">No</span></span>|<span data-ttu-id="49fbf-112">Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.</span><span class="sxs-lookup"><span data-stu-id="49fbf-112">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="49fbf-113">Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="49fbf-113">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="49fbf-114">Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)</span><span class="sxs-lookup"><span data-stu-id="49fbf-114">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="49fbf-115">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="49fbf-115">Examples:</span></span><br /><br /> <span data-ttu-id="49fbf-116">Servidor = MyServer</span><span class="sxs-lookup"><span data-stu-id="49fbf-116">Server=MyServer</span></span><br /><br /> <span data-ttu-id="49fbf-117">Servidor = MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="49fbf-117">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="49fbf-118">Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="49fbf-118">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="49fbf-119">**/ Base de datos** (o **/D**, vea la sección Comentarios)</span><span class="sxs-lookup"><span data-stu-id="49fbf-119">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="49fbf-120">No</span><span class="sxs-lookup"><span data-stu-id="49fbf-120">No</span></span>|<span data-ttu-id="49fbf-121">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="49fbf-121">Name of the BizTalk Management database.</span></span> <span data-ttu-id="49fbf-122">Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="49fbf-122">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="49fbf-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49fbf-123">Sample</span></span>  
 <span data-ttu-id="49fbf-124">**BTSTask ListApps**</span><span class="sxs-lookup"><span data-stu-id="49fbf-124">**BTSTask ListApps**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49fbf-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="49fbf-125">Remarks</span></span>  
 <span data-ttu-id="49fbf-126">Los parámetros no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="49fbf-126">Parameters are not case-sensitive.</span></span> <span data-ttu-id="49fbf-127">No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="49fbf-127">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49fbf-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="49fbf-128">See Also</span></span>  
 [<span data-ttu-id="49fbf-129">Referencia de línea de comandos de BTSTask</span><span class="sxs-lookup"><span data-stu-id="49fbf-129">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)