---
title: No se puede obtener el esquema del enlace para validar la dirección | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b002084a-63ae-4685-8ce3-88cc6489e19e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2032decfdf59ae175f3ee8fc686341c8a4061fc6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991341"
---
# <a name="cannot-obtain-scheme-from-binding-to-validate-address"></a>No se puede obtener el esquema del enlace para validar la dirección
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |               No se puede obtener el esquema del enlace para validar la dirección.               |
  
## <a name="explanation"></a>Explicación  
 El elemento de enlace de transporte que se ha especificado no tiene esquema.  
  
## <a name="user-action"></a>Acción del usuario  
 Asegúrese de que el elemento de enlace de transporte tiene un esquema válido, o que esté seleccionado un elemento de enlace de transporte válido. Si usa un enlace personalizado, asegúrese de que se especifique un elemento de enlace de transporte válido.  
  
 Para obtener más información, consulte los siguientes recursos en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda:  
  
-   [Configuración del adaptador de WCF-Custom](../core/configuring-the-wcf-custom-adapter.md)