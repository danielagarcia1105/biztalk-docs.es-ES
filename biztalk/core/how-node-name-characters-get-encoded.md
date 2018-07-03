---
title: Cómo se codifican los caracteres de nombre de nodo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6462856b-7a52-40c9-9aff-c0579130eec9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f374f9ebdfabfff1cc123fe2ad2f9d05a2b3c63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994061"
---
# <a name="how-node-name-characters-get-encoded"></a><span data-ttu-id="c69e6-102">Cómo se codifican los caracteres de los nombres de nodo</span><span class="sxs-lookup"><span data-stu-id="c69e6-102">How Node Name Characters Get Encoded</span></span>
<span data-ttu-id="c69e6-103">Si usa un carácter que no se permite en un nombre de nodo, el Editor de BizTalk le pide, que le pregunta si desea continuar con el carácter no permitido o caracteres codificados (**Aceptar** o **cancelar**).</span><span class="sxs-lookup"><span data-stu-id="c69e6-103">If you use a character that is not allowed in a node name, BizTalk Editor prompts you, asking if you want to proceed with the disallowed character or characters encoded (**OK** or **Cancel**).</span></span> <span data-ttu-id="c69e6-104">Si continúa, los caracteres no permitidos se codificarán del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c69e6-104">If you proceed, each disallowed character is encoded as follows:</span></span>  
  
- <span data-ttu-id="c69e6-105">Caracteres no permitidos se codifican como "*xDDDD\\*" donde "DDDD" es la representación hexadecimal de Unicode de 4 dígitos del carácter.</span><span class="sxs-lookup"><span data-stu-id="c69e6-105">Disallowed characters are encoded as "*xDDDD\\*" where "DDDD" is the 4-digit hexadecimal Unicode representation of the character.</span></span> <span data-ttu-id="c69e6-106">Por ejemplo, el carácter de espacio (0 x 0020) se codifica como "*x0020\\*".</span><span class="sxs-lookup"><span data-stu-id="c69e6-106">For example, the space character (0x0020) is encoded as "*x0020\\*".</span></span>  
  
- <span data-ttu-id="c69e6-107">Si se codifican dos o más caracteres no permitidos adyacentes, solo se utiliza un carácter de subrayado entre ellos.</span><span class="sxs-lookup"><span data-stu-id="c69e6-107">If two or more adjacent disallowed characters are encoded, only a single underscore character is used between them.</span></span> <span data-ttu-id="c69e6-108">Por ejemplo, tres espacios se codifican como "*x0020_x0020_x0020\\*"en lugar de"*x0020\__x0020\__x0020\\*".</span><span class="sxs-lookup"><span data-stu-id="c69e6-108">For example, three spaces are encoded as "*x0020_x0020_x0020\\*" rather than "*x0020\__x0020\__x0020\\*".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c69e6-109">Puede deshabilitarla para codificación de nombres de nodo estableciendo el **Mostrar diálogo de advertencia de codificación** propiedad **False** en la carpeta Editor de BizTalk de la **opciones** cuadro de diálogo disponible en el **herramientas** menú, o bien seleccionando la **no mostrar este cuadro de diálogo en el futuro** casilla de verificación en el nombre del nodo cuadro de diálogo de codificación.</span><span class="sxs-lookup"><span data-stu-id="c69e6-109">You can disable prompting for node name encoding by setting the **Show Encode Warning Dialog** property to **False** in the BizTalk Editor folder of the **Options** dialog box, available on the **Tools** menu, or by selecting the **Do not show this dialog in the future** check box in the node name encoding dialog box.</span></span> <span data-ttu-id="c69e6-110">Para obtener más información acerca de las opciones en este cuadro de diálogo, vea [administrar la vista de árbol de esquema](../core/how-to-manage-the-schema-tree-view.md).</span><span class="sxs-lookup"><span data-stu-id="c69e6-110">For more information about the options in this dialog box, see [Managing the Schema Tree View](../core/how-to-manage-the-schema-tree-view.md).</span></span>  
  
 <span data-ttu-id="c69e6-111">La vista de árbol de esquema del Editor de BizTalk muestra los nombres de nodo con los caracteres que el usuario escribe.</span><span class="sxs-lookup"><span data-stu-id="c69e6-111">The schema tree view in BizTalk Editor displays node names by using the characters you type.</span></span> <span data-ttu-id="c69e6-112">El Asignador de BizTalk también muestra los caracteres que el usuario escribe en lugar de la versión codificada.</span><span class="sxs-lookup"><span data-stu-id="c69e6-112">BizTalk Mapper also displays the characters you have typed rather than the encoded version.</span></span> <span data-ttu-id="c69e6-113">En la vista XSD del Editor de BizTalk y en el propio archivo XSD se utiliza en cambio el nombre de nodo codificado.</span><span class="sxs-lookup"><span data-stu-id="c69e6-113">In the XSD view of BizTalk Editor, and in the XSD file itself, the encoded node name is used.</span></span> <span data-ttu-id="c69e6-114">Por ejemplo, si asigna el nombre Purchase Order a un nodo, el nodo se mostrará como Purchase Order en los árboles de esquema tanto en el Editor de BizTalk como en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c69e6-114">For example, if you name a node Purchase Order, it will be displayed as Purchase Order in the schema trees in both BizTalk Editor and BizTalk Mapper.</span></span> <span data-ttu-id="c69e6-115">En la vista XSD del Editor de BizTalk, el nodo del elemento correspondiente, cuando se inserte por primera vez, será el que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="c69e6-115">In the XSD view of BizTalk Editor, the corresponding element node, when first inserted, will be as follows.</span></span>  
  
```  
<element name="Purchase_x0020_Order" type="xs:string />  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c69e6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c69e6-116">See Also</span></span>  
 <span data-ttu-id="c69e6-117">[Propiedad Node Name](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="c69e6-117">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="c69e6-118">Caracteres de los nombres de nodo que se codifican</span><span class="sxs-lookup"><span data-stu-id="c69e6-118">Which Node Name Characters Get Encoded</span></span>](../core/which-node-name-characters-get-encoded.md)