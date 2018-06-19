---
title: Editor desplegable personalizado para la configuración del adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1b0961-652f-42b8-a18a-17abe9542cdd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88e5eb887c2177783611ada8e3ce2a80a0b6a66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238500"
---
# <a name="custom-drop-down-editor-for-adapter-configuration"></a><span data-ttu-id="70cad-102">Editor desplegable personalizado para la configuración del adaptador</span><span class="sxs-lookup"><span data-stu-id="70cad-102">Custom Drop-Down Editor for Adapter Configuration</span></span>
<span data-ttu-id="70cad-103">El código del editor personalizado muestra un editor derivado de la **System.Drawing.Design.UITypeEditor** clase, que muestra un cuadro de texto de la lista desplegable para especificar una contraseña.</span><span class="sxs-lookup"><span data-stu-id="70cad-103">The code for the custom editor shows an editor derived from the **System.Drawing.Design.UITypeEditor** class that displays a drop-down text box for entering a password.</span></span> <span data-ttu-id="70cad-104">El **GetEditStyle** invalidar devuelve **UIEditorEditStyle.DropDown** para indicar un subcontrol desplegable.</span><span class="sxs-lookup"><span data-stu-id="70cad-104">The **GetEditStyle** override returns **UIEditorEditStyle.DropDown** to indicate a drop-down subcontrol.</span></span> <span data-ttu-id="70cad-105">Los métodos de servicio **DropDownControl** y **CloseDropDown** administrar el control creado con **CreatePassword**.</span><span class="sxs-lookup"><span data-stu-id="70cad-105">The service methods **DropDownControl** and **CloseDropDown** manage the control created with **CreatePassword**.</span></span>  
  
 <span data-ttu-id="70cad-106">El código siguiente es la definición de clase del editor desplegable personalizado:</span><span class="sxs-lookup"><span data-stu-id="70cad-106">The following code is the class definition for the custom drop-down editor:</span></span>  
  
```  
/*************************************************************************  
 * Copyright (c) 1999-2004 Microsoft Corporation. All rights reserved.   *  
 *                                                                       *  
 * THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY *  
 * KIND, WHETHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE  *  
 * IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A PARTICULAR *  
 * PURPOSE. THE ENTIRE RISK OF USE OR RESULTS IN CONNECTION WITH THE USE *  
 * OF THIS CODE AND INFORMATION REMAINS WITH THE USER.                   *  
 *************************************************************************/  
  
using System;  
using System.ComponentModel;  
using System.Drawing.Design;  
using System.Windows.Forms;  
using System.Windows.Forms.Design;  
using System.Security;  
using System.Security.Permissions;  
using Microsoft.BizTalk.Adapter.Framework;  
using Microsoft.BizTalk.Adapter.Framework.Forms;  
  
namespace AdapterManagement.ComponentModel {  
   /// <summary>  
   /// PasswordUITypeEditor implements a user interface for acquiring passwords  
   /// within a visual designer.  
   /// </summary>  
   public class PasswordUITypeEditor : UITypeEditor {  
      public const char PasswordChar = '\u25cf';  
      private IWindowsFormsEditorService _service = null;  
      private TextBox _password = null;  
  
      [SecurityPermissionAttribute(SecurityAction.LinkDemand)]  
      public override UITypeEditorEditStyle GetEditStyle(ITypeDescriptorContext context) {  
         if (null != context && null != context.Instance) {  
            return UITypeEditorEditStyle.DropDown;  
         }  
         return base.GetEditStyle(context);  
      }  
  
      [SecurityPermissionAttribute(SecurityAction.LinkDemand)]  
      public override object EditValue(ITypeDescriptorContext context,   
                               IServiceProvider provider,  
                               object value) {  
         if (null != context && null != context.Instance && null != provider) {  
            this._service = (IWindowsFormsEditorService) provider.GetService   
                        (typeof(IWindowsFormsEditorService));  
            if (null != this._service) {  
               this._password = CreatePassword();  
               this._service.DropDownControl(this._password);  
               value = this._password.Text;  
            }  
         }  
         return value;  
      }  
  
      private TextBox CreatePassword () {  
         TextBox password = new TextBox();  
         password.PasswordChar = PasswordUITypeEditor.PasswordChar;  
         password.Leave += new EventHandler(password_Leave);  
      }  
  
      private void password_Leave(object sender, EventArgs e) {  
         if (null != this._service) {  
            this._service.CloseDropDown();  
         }  
      }  
   } // PasswordUITypeEditor  
} // Microsoft.BizTalk.Adapter.Framework.ComponentModel  
```  
  
## <a name="see-also"></a><span data-ttu-id="70cad-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="70cad-107">See Also</span></span>  
 <span data-ttu-id="70cad-108">[Diseñador de configuración de adaptador personalizado](../core/custom-adapter-configuration-designer.md) </span><span class="sxs-lookup"><span data-stu-id="70cad-108">[Custom Adapter Configuration Designer](../core/custom-adapter-configuration-designer.md) </span></span>  
 <span data-ttu-id="70cad-109">[Editor de cuadro de diálogo Modal personalizado para la configuración del adaptador](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="70cad-109">[Custom Modal Dialog Editor for Adapter Configuration](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="70cad-110">[Convertidor de tipos personalizado para la configuración del adaptador](../core/custom-type-converter-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="70cad-110">[Custom Type Converter for Adapter Configuration](../core/custom-type-converter-for-adapter-configuration.md) </span></span>  
 [<span data-ttu-id="70cad-111">Componentes de configuración avanzada para adaptadores</span><span class="sxs-lookup"><span data-stu-id="70cad-111">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)