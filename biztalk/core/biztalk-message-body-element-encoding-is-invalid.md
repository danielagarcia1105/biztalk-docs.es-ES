---
title: Codificación de elemento de cuerpo de mensaje de BizTalk Server no es válido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b407e5c3-4655-4b2f-8ecc-30eb080ec47c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b1835371e5c042d3ddc46558cbf97970f6bfc6c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "25964818"
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a>Codificación de elemento de cuerpo de mensaje de BizTalk no válida
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Codificación de elemento de cuerpo de mensaje de BizTalk "{0}" no válida. Codificación esperada: "xml", "base64", "hex" o "cadena"|  
  
## <a name="explanation"></a>Explicación  
 Este error indica el uso de la opción de plantilla de cuerpo de BizTalk para los mensajes salientes. Sin embargo, el tipo de codificación especificado para el cuerpo de BizTalk no es válido.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar el tipo de codificación.  
  
#### <a name="to-configure-the-encoding-type"></a>Para configurar el tipo de codificación  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **mensajes** ficha.  
  
9. En el **cuerpo del mensaje saliente de WCF** sección, haga clic en el **plantilla: contenido especificado por plantilla** botón de radio. En el **XML** cuadro de texto, el formato del cuerpo de BizTalk debe ser   
    \<**BTS-msg-body xmlns = "http://www.microsoft.com/schemas/bts2007" codificación = "[xml&#124;base64&#124;hexadecimal&#124;cadena]" /** \> (los valores válidos, que distinguen mayúsculas de minúsculas, para la codificación son xml&#124;base64&#124;hexadecimal&#124;cadena)