---
title: Crear o editar una configuración de procesos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process configuration, modifying
- process configuration, creating
- creating, process configuration
- modifying, process configuration
ms.assetid: 39cc2c93-0986-48d3-8c6f-4280ec9af4e0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32300e84d2c9102baaa68a57045fefc103d0d9e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013165"
---
# <a name="creating-or-editing-a-process-configuration"></a><span data-ttu-id="5d482-102">Crear o editar una configuración de procesos</span><span class="sxs-lookup"><span data-stu-id="5d482-102">Creating or Editing a Process Configuration</span></span>
<span data-ttu-id="5d482-103">Esta sección describe cómo crear o editar una configuración de procesos para implementar un proceso de interfaz de socio (PIP) en Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d482-103">This section describes how to create or edit a process configuration to implement a Partner Interface Process (PIP) in Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="5d482-104">Un PIP de RosettaNet define un cuadro de diálogo de procesos empresariales entre dos socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="5d482-104">A RosettaNet PIP defines a business-process dialog between two trading partners.</span></span> <span data-ttu-id="5d482-105">En [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], para crear una PIP con un compañero, primero debe crear una configuración de procesos.</span><span class="sxs-lookup"><span data-stu-id="5d482-105">In [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], to create a PIP with a partner, you must first create a process configuration.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5d482-106"> Este perfil se usa para almacenar todas las características de configuración del PIP.</span><span class="sxs-lookup"><span data-stu-id="5d482-106"> uses this profile to store all configuration characteristics of the PIP.</span></span> <span data-ttu-id="5d482-107">A continuación, puede usar esta configuración para crear un acuerdo con el socio comercial.</span><span class="sxs-lookup"><span data-stu-id="5d482-107">You can then use this configuration to create an agreement with the partner.</span></span>  
  
 <span data-ttu-id="5d482-108">Para obtener información acerca de las propiedades de configuración de procesos y procedimientos para crear o editar una configuración de procesos, vea [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="5d482-108">For information about process configuration properties, and procedures for creating or editing a process configuration, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="5d482-109">Al crear una nueva configuración de proceso, debe basar la configuración en el documento de especificación de PIP mantenida por la organización RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="5d482-109">In creating a new process configuration, you must base the settings on the PIP specification document maintained by the RosettaNet organization.</span></span> <span data-ttu-id="5d482-110">Configuración del proceso todos los valores proceden de las especificaciones de PIP y [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] rellena la mayoría de los parámetros con valores predeterminados que son los valores que normalmente se usan más de los campos.</span><span class="sxs-lookup"><span data-stu-id="5d482-110">All process configuration settings come from the PIP specifications, and [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] populates most of the settings with default values that are the most typically used values for the fields.</span></span> <span data-ttu-id="5d482-111">Debe comprobar que la configuración se corresponde con los valores de la especificación de PIP adecuado.</span><span class="sxs-lookup"><span data-stu-id="5d482-111">You must verify that the settings correspond to the values in the appropriate PIP specification.</span></span> <span data-ttu-id="5d482-112">Para obtener más información acerca de cómo se asignan los valores de PIP que escriba las instrucciones de la especificación de PIP, consulte [mediante la especificación de PIP para crear una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="5d482-112">For more information about how the PIP settings that you enter map to the guidance in the PIP specification, see [Using the PIP Specification to Create a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="5d482-113">La configuración del proceso puede ser para RosettaNet o CIDX (intercambio de datos de la industria química).</span><span class="sxs-lookup"><span data-stu-id="5d482-113">The process configuration can be for either RosettaNet or CIDX (Chemical Industry Data Exchange).</span></span> <span data-ttu-id="5d482-114">Para obtener información acerca de una configuración CIDX, consulte [configuración CIDX las normas europeas de intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span><span class="sxs-lookup"><span data-stu-id="5d482-114">For information about a CIDX configuration, see [Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5d482-115"> no admite el cambio de una configuración de procesos mientras hay procesos activos.</span><span class="sxs-lookup"><span data-stu-id="5d482-115"> does not support changing a process configuration while there are active processes.</span></span> <span data-ttu-id="5d482-116">Si lo hace, los procesos activos se completará con errores.</span><span class="sxs-lookup"><span data-stu-id="5d482-116">If you do so, the active processes will complete with failures.</span></span> <span data-ttu-id="5d482-117">Todos los nuevos procesos correctamente recogerá la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="5d482-117">All new processes will successfully pick up the new configuration settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d482-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5d482-118">In This Section</span></span>  
  
-   [<span data-ttu-id="5d482-119">Cómo crear o editar una configuración de procesos</span><span class="sxs-lookup"><span data-stu-id="5d482-119">How to Create or Edit a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)  
  
-   [<span data-ttu-id="5d482-120">Uso de la especificación de PIP para crear una configuración de procesos</span><span class="sxs-lookup"><span data-stu-id="5d482-120">Using the PIP Specification to Create a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)  
  
-   [<span data-ttu-id="5d482-121">Propiedades de autorización y no rechazo</span><span class="sxs-lookup"><span data-stu-id="5d482-121">Authorization and Non-Repudiation Properties</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)  
  
-   [<span data-ttu-id="5d482-122">Configuración del intercambio de mensajes de normas europeas de intercambio de datos para CIDX</span><span class="sxs-lookup"><span data-stu-id="5d482-122">Setting Up CIDX eStandards Message Exchange</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)