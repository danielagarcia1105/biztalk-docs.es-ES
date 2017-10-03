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
# <a name="advanced-configuration-components-for-adapters"></a>Componentes de configuración avanzada para adaptadores
El Marco de trabajo de adaptadores de BizTalk es compatible con un editor desplegable personalizado, un editor de cuadro de diálogo modal personalizado y con un convertidor de tipos personalizado. Estos componentes de diseño personalizado son especialmente útiles al tomar la información de nombre de usuario y contraseña como entrada.  
  
 Puede invocar un editor personalizado o convertidor de tipos para un campo de datos concreto (elemento o atributo) en el esquema de configuración. Como se describe en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ayuda, el editor debe derivarse de **System.Drawing.Design.UITypeEditor** y el convertidor de tipos de **System.ComponentModel.TypeConverter**.  
  
 Un editor reemplaza mínimamente el **GetEditStyle** método para especificar el tipo de editor (**Modal** cuadro de diálogo, **desplegable** (control), o **ninguno**de los pasos anteriores) y la **EditValue** método para cambiar el valor con el editor.  
  
 Un convertidor de tipos normalmente reemplaza el **ConvertFrom**, **CanConvertFrom**, **ConvertTo**, **CanConvertTo**,  **GetStandardValues**, **GetStandardValuesSupported**, y **GetStandardValuesExclusive**métodos de la biblioteca de clases de .NET Framework.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Diseñador de configuración de adaptador personalizado](../core/custom-adapter-configuration-designer.md)  
  
-   [Editor desplegable personalizado para la configuración del adaptador](../core/custom-drop-down-editor-for-adapter-configuration.md)  
  
-   [Editor de cuadro de diálogo Modal personalizado para la configuración del adaptador](../core/custom-modal-dialog-editor-for-adapter-configuration.md)  
  
-   [Convertidor de tipos personalizado para la configuración del adaptador](../core/custom-type-converter-for-adapter-configuration.md)