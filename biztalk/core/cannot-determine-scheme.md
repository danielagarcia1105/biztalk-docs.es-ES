---
title: No se puede determinar el esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cc6e50b-33f5-4a88-b35d-075fdf8d79b2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6086562f593b7ca04db63b7fb41f5cf128afe9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007173"
---
# <a name="cannot-determine-scheme"></a>No se puede determinar el esquema
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                 No se puede determinar el esquema; especifique un enlace válido.                  |
  
## <a name="explanation"></a>Explicación  
 El elemento de enlace de transporte que se ha especificado no tiene esquema.  
  
## <a name="user-action"></a>Acción del usuario  
 Seleccione un enlace válido y asegúrese de que el elemento de enlace de transporte tenga un esquema válido. Si usa un enlace personalizado, asegúrese de que se especifique un elemento de enlace de transporte válido.  
  
 Para obtener más información, consulte los siguientes recursos en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda:  
  
-   [Configuración del adaptador de WCF-Custom](../core/configuring-the-wcf-custom-adapter.md)