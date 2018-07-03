---
title: Desarrollar un componente de canalización generales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63f5d8d1-30fb-4a1e-b4bd-2be07b618b20
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ca387b139a32606dea89f7c931c86245d151dcb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966693"
---
# <a name="developing-a-general-pipeline-component"></a><span data-ttu-id="0e9b5-102">Desarrollar un componente de canalización generales</span><span class="sxs-lookup"><span data-stu-id="0e9b5-102">Developing a General Pipeline Component</span></span>

## <a name="interfaces"></a><span data-ttu-id="0e9b5-103">Interfaces</span><span class="sxs-lookup"><span data-stu-id="0e9b5-103">Interfaces</span></span>
<span data-ttu-id="0e9b5-104">Un componente general de canalización consiste en un componente .NET o COM que implementa las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e9b5-104">A general pipeline component is a .NET or COM component that implements the following interfaces:</span></span>  
  
- <span data-ttu-id="0e9b5-105">Interfaz IBaseComponent (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0e9b5-105">IBaseComponent Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
- <span data-ttu-id="0e9b5-106">IComponent (interfaz) (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0e9b5-106">IComponent Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
- <span data-ttu-id="0e9b5-107">Interfaz IComponentUI (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0e9b5-107">IComponentUI Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
- [<span data-ttu-id="0e9b5-108">IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="0e9b5-108">IPersistPropertyBag</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.ipersistpropertybag)
  
  <span data-ttu-id="0e9b5-109">Un componente general de canalización recibe un mensaje del motor de mensajería de BizTalk, lo procesa y lo devuelve al motor de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e9b5-109">A general pipeline component gets one message from the BizTalk Messaging Engine, processes it, and returns it to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine.</span></span> <span data-ttu-id="0e9b5-110">Los componentes generales también pueden implementarse de modo que no devuelvan mensajes al servidor.</span><span class="sxs-lookup"><span data-stu-id="0e9b5-110">General components can also be implemented so that they do not return messages to the server.</span></span> <span data-ttu-id="0e9b5-111">A estos componentes se les denomina componentes consumidores porque el componente recibe mensajes, pero no genera ningún mensaje de resultado.</span><span class="sxs-lookup"><span data-stu-id="0e9b5-111">Such components are called consuming components because the component receives messages but does not produce any result messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e9b5-112">Los componentes de canalización personalizados deberían copiar todas las partes adicionales del mensaje de entrada en los mensajes de salida.</span><span class="sxs-lookup"><span data-stu-id="0e9b5-112">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="0e9b5-113">Con ello, se conservan para el procesamiento ulterior en la canalización.</span><span class="sxs-lookup"><span data-stu-id="0e9b5-113">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="more-pipeline-resources"></a><span data-ttu-id="0e9b5-114">Más recursos de la canalización</span><span class="sxs-lookup"><span data-stu-id="0e9b5-114">More pipeline resources</span></span>
 <span data-ttu-id="0e9b5-115">[Desarrollar un componente de canalización de ensamblado](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="0e9b5-115">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="0e9b5-116">[Desarrollar un componente de canalización de desensamblado](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="0e9b5-116">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="0e9b5-117">[Desarrollar un componente de canalización de búsqueda](../core/developing-a-probing-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="0e9b5-117">[Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md) </span></span>  
 <span data-ttu-id="0e9b5-118">[Informes de errores de componentes de canalización](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="0e9b5-118">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="0e9b5-119">[Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="0e9b5-119">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="0e9b5-120">[Implementar componentes de canalización](../core/deploying-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="0e9b5-120">[Deploying Pipeline Components](../core/deploying-pipeline-components.md) </span></span>  
 [<span data-ttu-id="0e9b5-121">CustomComponent (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="0e9b5-121">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)