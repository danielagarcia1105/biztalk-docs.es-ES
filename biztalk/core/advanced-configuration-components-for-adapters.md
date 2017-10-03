---
title: "Advanced componentes de configuración para los adaptadores | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb31b996-6959-4b5a-9a9f-f48fd91a6180
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8307f54caffec269466dcd9398a9d911fdc83715
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="advanced-configuration-components-for-adapters"></a><span data-ttu-id="07d9c-102">Componentes de configuración avanzada para adaptadores</span><span class="sxs-lookup"><span data-stu-id="07d9c-102">Advanced Configuration Components for Adapters</span></span>
<span data-ttu-id="07d9c-103">El Marco de trabajo de adaptadores de BizTalk es compatible con un editor desplegable personalizado, un editor de cuadro de diálogo modal personalizado y con un convertidor de tipos personalizado.</span><span class="sxs-lookup"><span data-stu-id="07d9c-103">The BizTalk Adapter Framework supports a custom drop-down editor, a custom modal dialog editor, and a custom type converter.</span></span> <span data-ttu-id="07d9c-104">Estos componentes de diseño personalizado son especialmente útiles al tomar la información de nombre de usuario y contraseña como entrada.</span><span class="sxs-lookup"><span data-stu-id="07d9c-104">These custom design components are especially useful when taking user name and password information as input.</span></span>  
  
 <span data-ttu-id="07d9c-105">Puede invocar un editor personalizado o convertidor de tipos para un campo de datos concreto (elemento o atributo) en el esquema de configuración.</span><span class="sxs-lookup"><span data-stu-id="07d9c-105">You can invoke a custom editor or type converter for a specific data field (element or attribute) in the configuration schema.</span></span> <span data-ttu-id="07d9c-106">Como se describe en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ayuda, el editor debe derivarse de **System.Drawing.Design.UITypeEditor** y el convertidor de tipos de **System.ComponentModel.TypeConverter**.</span><span class="sxs-lookup"><span data-stu-id="07d9c-106">As described in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help, the editor must be derived from **System.Drawing.Design.UITypeEditor** and the type converter from **System.ComponentModel.TypeConverter**.</span></span>  
  
 <span data-ttu-id="07d9c-107">Un editor reemplaza mínimamente el **GetEditStyle** método para especificar el tipo de editor (**Modal** cuadro de diálogo, **desplegable** (control), o **ninguno**de los pasos anteriores) y la **EditValue** método para cambiar el valor con el editor.</span><span class="sxs-lookup"><span data-stu-id="07d9c-107">An editor minimally overrides the **GetEditStyle** method to specify the kind of editor (**Modal** dialog, **DropDown** control, or **None** of the above) and the **EditValue** method to change the value with the editor.</span></span>  
  
 <span data-ttu-id="07d9c-108">Un convertidor de tipos normalmente reemplaza el **ConvertFrom**, **CanConvertFrom**, **ConvertTo**, **CanConvertTo**,  **GetStandardValues**, **GetStandardValuesSupported**, y **GetStandardValuesExclusive**métodos de la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="07d9c-108">A type converter typically overrides the **ConvertFrom**, **CanConvertFrom**, **ConvertTo**, **CanConvertTo**, **GetStandardValues**, **GetStandardValuesSupported**, and **GetStandardValuesExclusive**methods of the .NET Framework Class Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07d9c-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="07d9c-109">In This Section</span></span>  
  
-   [<span data-ttu-id="07d9c-110">Diseñador de configuración de adaptador personalizado</span><span class="sxs-lookup"><span data-stu-id="07d9c-110">Custom Adapter Configuration Designer</span></span>](../core/custom-adapter-configuration-designer.md)  
  
-   [<span data-ttu-id="07d9c-111">Editor desplegable personalizado para la configuración del adaptador</span><span class="sxs-lookup"><span data-stu-id="07d9c-111">Custom Drop-Down Editor for Adapter Configuration</span></span>](../core/custom-drop-down-editor-for-adapter-configuration.md)  
  
-   [<span data-ttu-id="07d9c-112">Editor de cuadro de diálogo Modal personalizado para la configuración del adaptador</span><span class="sxs-lookup"><span data-stu-id="07d9c-112">Custom Modal Dialog Editor for Adapter Configuration</span></span>](../core/custom-modal-dialog-editor-for-adapter-configuration.md)  
  
-   [<span data-ttu-id="07d9c-113">Convertidor de tipos personalizado para la configuración del adaptador</span><span class="sxs-lookup"><span data-stu-id="07d9c-113">Custom Type Converter for Adapter Configuration</span></span>](../core/custom-type-converter-for-adapter-configuration.md)