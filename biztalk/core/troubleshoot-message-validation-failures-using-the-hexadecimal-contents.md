---
title: "Solución de problemas de errores de validación de mensajes mediante la visualización del contenido Hexadecimal de mensajes suspendidos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf14cd9-2d4b-43a3-9738-52bfd879e1e4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f7dc0f24a85f206831e3706bd03f2206aaa2c15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-message-validation-failures-by-viewing-the-hexadecimal-contents-of-suspended-messages"></a>Solucionar problemas relacionados con errores de validación de mensajes mediante la visualización del contenido hexadecimal de los mensajes suspendidos
Si un mensaje se suspende debido a errores de validación, puede resultar útil ver la representación hexadecimal de las partes del mensaje para determinar la causa del error de validación. En este tema se enumeran los pasos que pueden llevarse a cabo para ver la representación hexadecimal de las partes de un mensaje suspendido.  
  
## <a name="use-the-message-details-dialog-box-to-view-message-parts"></a>Usar el cuadro de diálogo Detalles del mensaje para ver las partes de los mensajes  
 Para ver la representación hexadecimal de las partes de un mensaje, siga estos pasos:  
  
1.  Use la **consulta** pestaña en la consola de administración de BizTalk para devolver un conjunto de resultados con uno o varios mensajes suspendidos. Vea [cómo buscar mensajes](../core/how-to-search-for-messages.md) para obtener más información.  
  
2.  Haga doble clic en el mensaje suspendido que desea investigar para mostrar el **detalles del mensaje** cuadro de diálogo para el mensaje.  
  
3.  Haga clic en una parte del mensaje en el panel izquierdo de la **detalles del mensaje** cuadro de diálogo para mostrar la parte del mensaje.  
  
    > [!NOTE]
    >  Los mensajes pueden constar de 0, 1 o varias partes. Los mensajes suelen tener una sola parte a la que se denomina "cuerpo".  
  
4.  Haga clic en el **binario** en el panel derecho de la **detalles del mensaje** cuadro de diálogo para mostrar la representación hexadecimal de la parte del mensaje.  
  
5.  Examine la representación hexadecimal de caracteres en las partes del mensaje para comprobar lo siguiente:  
  
    -   Marca de orden de bytes no válida o que falta. Para obtener más información sobre el orden de bytes sobre marcas, consulte [http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380).  
  
    -   Diferencias entre la codificación de los saltos de línea en Unix y Windows. Unix emplea el avance de línea hexadecimal (0A) para indicar un salto de línea, mientras que Windows utiliza tanto el retorno de carro hexadecimal (0D) como el avance de línea (0A) para indicarlo.  
  
    -   Caracteres de control no válidos en partes del mensaje. Los caracteres de control en partes del mensaje que no se muestran en la vista de texto pueden verse en la vista binaria.  
  
    -   Caracteres nulos no válidos en la mitad de una parte del mensaje que pueden ocasionar que ésta se trunque. El carácter nulo se representa como (00) en formato hexadecimal.  
  
    -   Desplazamiento de caracteres no válido en archivos sin formato posicionales. Observe la representación hexadecimal de una parte del mensaje para ver el desplazamiento de datos en un archivo sin formato posicional.  
  
## <a name="see-also"></a>Vea también  
 [Investigación de orquestación, puerto y errores de mensaje](../core/investigating-orchestration-port-and-message-failures.md)