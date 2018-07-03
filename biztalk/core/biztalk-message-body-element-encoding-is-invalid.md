---
title: Codificación de elemento de cuerpo de mensaje de BizTalk Server no es válido | Microsoft Docs
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
ms.openlocfilehash: c6bca7046606461dd3368224364c21dd48ea5dfb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967973"
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a>Codificación de elemento de cuerpo de mensaje de BizTalk no válida
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| Versión del producto |                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                           |
|    Identificador del evento     |                                                       0                                                        |
|  Origen del evento   |                                                       0                                                        |
|    Componente    |                                                       0                                                        |
|  Nombre simbólico  |                                                       0                                                        |
|  Texto del mensaje   | Codificación del elemento del cuerpo del mensaje de BizTalk "{0}" no es válido. Codificación esperada: "xml", "base64", "hex" o "string" |
  
## <a name="explanation"></a>Explicación  
 Este error indica el uso de la opción de plantilla de cuerpo de BizTalk para los mensajes salientes. Sin embargo, el tipo de codificación especificado para el cuerpo de BizTalk no es válido.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar el tipo de codificación.  
  
#### <a name="to-configure-the-encoding-type"></a>Para configurar el tipo de codificación  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3. Busque la aplicación y, a continuación, busque su transporte.  
  
4. Haga clic con el botón secundario en el nombre del transporte.  
  
5. Haga clic en **Propiedades**.  
  
6. En el puerto **tipo** lista, seleccione el puerto correcto.  
  
7. Haga clic en **configurar**.  
  
8. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **mensajes** ficha.  
  
9. En el **cuerpo del mensaje saliente de WCF** sección, haga clic en el **plantilla – contenido especificado por plantilla** botón de radio. En el **XML** cuadro de texto, debe ser el formato del cuerpo de BizTalk   
    \<**BTS-msg-body xmlns = "<http://www.microsoft.com/schemas/bts2007>" encoding = "[xml&#124;base64&#124;hexadecimal&#124;string]" /** \> (los valores válidos, que distinguen mayúsculas de minúsculas, para la codificación son xml&#124;base64&#124;hexadecimal&#124;cadena)