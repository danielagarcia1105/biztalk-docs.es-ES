---
title: Funciones (nodo servicio) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Roles node [binding file]
ms.assetid: 847755c9-1697-41a0-b870-f9e795a1a2a6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b47f5ae94326b0555c0c9cd84752cb9f1c409daa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268404"
---
# <a name="roles-service-node"></a><span data-ttu-id="1dca0-102">Funciones (nodo Servicio)</span><span class="sxs-lookup"><span data-stu-id="1dca0-102">Roles (Service Node)</span></span>
<span data-ttu-id="1dca0-103">El nodo Roles de un archivo de enlace es el nodo primario de todos los nodos de rol que proporcionan información específica acerca del enlazado de cada rol a un servicio que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="1dca0-103">The Roles node of a binding file is the parent node for all of the Role nodes which provide specific information about each role bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-roles-node"></a><span data-ttu-id="1dca0-104">Nodos del nodo Roles</span><span class="sxs-lookup"><span data-stu-id="1dca0-104">Nodes in the Roles node</span></span>  
 <span data-ttu-id="1dca0-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="1dca0-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="1dca0-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1dca0-106">**Name**</span></span>|<span data-ttu-id="1dca0-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="1dca0-107">**Node Type**</span></span>|<span data-ttu-id="1dca0-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="1dca0-108">**Data Type**</span></span>|<span data-ttu-id="1dca0-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="1dca0-109">**Description**</span></span>|<span data-ttu-id="1dca0-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="1dca0-110">**Restrictions**</span></span>|<span data-ttu-id="1dca0-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="1dca0-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="1dca0-112">Rol</span><span class="sxs-lookup"><span data-stu-id="1dca0-112">Role</span></span>](../core/role-roles-node.md)|<span data-ttu-id="1dca0-113">Grabar</span><span class="sxs-lookup"><span data-stu-id="1dca0-113">Record</span></span>|<span data-ttu-id="1dca0-114">RoleRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="1dca0-114">RoleRef (ComplexType)</span></span>|<span data-ttu-id="1dca0-115">Especifica información acerca de un rol que está enlazado a un servicio que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="1dca0-115">Specifies information about a role that is bound to a service that is exported with the binding file.</span></span>|<span data-ttu-id="1dca0-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="1dca0-116">Not required</span></span>|<span data-ttu-id="1dca0-117">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="1dca0-117">Default value: none</span></span>|