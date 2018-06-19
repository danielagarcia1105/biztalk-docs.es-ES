---
title: Vistas personalizadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9084cc07-be98-4c57-afea-4fa369a38bad
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184f49330374126f4afc0bd4bb376ea31a5ca681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238172"
---
# <a name="custom-views"></a>Vistas personalizadas
Una vista personalizada es normalmente un objeto de control de ventana de sólo lectura (derivado de **System.Windows.Forms.Control**) y se proporciona una extensión para representar el esquema en un formato de presentación personalizado para el tipo de archivo o archivos compatible mediante la extensión del Editor de BizTalk. Una extensión puede implementar varias vistas personalizadas, aunque no necesita tener ninguna vista personalizada.  
  
 Una vista personalizada se muestra como una vista adicional en el mismo panel del Editor de BizTalk que la vista XSD y se puede tener acceso a ella a través de las pestañas situadas en la parte inferior de las vistas. Por ejemplo, Extensión de archivo sin formato agrega una nueva vista con una pestaña con la etiqueta Archivo sin formato.  
  
## <a name="see-also"></a>Vea también  
 [Extender el Editor de BizTalk](../core/extending-biztalk-editor.md)