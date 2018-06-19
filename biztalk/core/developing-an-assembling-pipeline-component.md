---
title: Desarrollar un ensamblado de componente de canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IComponentUI interface, assembling
- IBaseComponent interface, assembling
- pipeline interfaces, IBaseComponent
- pipeline components [custom], interfaces
- pipeline interfaces, IComponentUI
- IAssemblerComponent interface, assembling
- pipeline interfaces, IAssemblerComponent
- pipeline components [custom], assembling
ms.assetid: 2f85421d-2010-4a36-82b5-ea8016f8aa99
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8de06a815e1c5a6bf71700ad373ae3f278b3a9a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239620"
---
# <a name="developing-an-assembling-pipeline-component"></a><span data-ttu-id="dafc1-102">Desarrollar un componente de canalización de ensamblado</span><span class="sxs-lookup"><span data-stu-id="dafc1-102">Developing an Assembling Pipeline Component</span></span>
<span data-ttu-id="dafc1-103">Un componente de canalización de ensamblado es un componente .NET o COM que recibe varios mensajes en la entrada y produce un mensaje en la salida.</span><span class="sxs-lookup"><span data-stu-id="dafc1-103">An assembling pipeline component is a .NET or COM component that receives several messages on input and produces one message on output.</span></span> <span data-ttu-id="dafc1-104">Los componentes de ensamblado se utilizan para recopilar documentos individuales en el lote de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="dafc1-104">Assembling components are used to collect individual documents into the message interchange batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dafc1-105">No se utiliza la funcionalidad de ensamblado, por lo que BizTalk Server siempre transfiere un documento a la entrada del componente.</span><span class="sxs-lookup"><span data-stu-id="dafc1-105">Assembly functionality is not used, so BizTalk Server always passes one document to the component input.</span></span>  
  
 <span data-ttu-id="dafc1-106">Un componentes de ensamblado debe implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="dafc1-106">An assembling component must implement the following interfaces:</span></span>  
  
-   `IBaseComponent`  
  
-   `IAssemblerComponent`
  
-   `IComponentUI`
  
-   <span data-ttu-id="dafc1-107">**IPersistPropertyBag.**</span><span class="sxs-lookup"><span data-stu-id="dafc1-107">**IPersistPropertyBag .**</span></span> <span data-ttu-id="dafc1-108">Consulte la documentación de .NET Framework SDK para esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="dafc1-108">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dafc1-109">Los componentes de canalización personalizados deberían copiar todas las partes adicionales del mensaje de entrada en los mensajes de salida.</span><span class="sxs-lookup"><span data-stu-id="dafc1-109">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="dafc1-110">Con ello, se conservan para el procesamiento ulterior en la canalización.</span><span class="sxs-lookup"><span data-stu-id="dafc1-110">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dafc1-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="dafc1-111">See Also</span></span>  
 <span data-ttu-id="dafc1-112">[Desarrollar un componente de canalización de General](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="dafc1-112">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="dafc1-113">[Desarrollar un componente de canalización de desensamblado](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="dafc1-113">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="dafc1-114">[Desarrollar un componente de canalización de búsqueda](../core/developing-a-probing-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="dafc1-114">[Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md) </span></span>  
 <span data-ttu-id="dafc1-115">[Informar de errores de componentes de canalización](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="dafc1-115">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="dafc1-116">[Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="dafc1-116">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="dafc1-117">[Implementar componentes de canalización](../core/deploying-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="dafc1-117">[Deploying Pipeline Components](../core/deploying-pipeline-components.md) </span></span>  
 [<span data-ttu-id="dafc1-118">CustomComponent (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="dafc1-118">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)