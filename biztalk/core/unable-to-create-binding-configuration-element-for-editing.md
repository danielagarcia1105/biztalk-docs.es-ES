---
title: No se puede crear el elemento de configuración de enlace para su edición | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71853662-5a4a-417e-8160-c93dbcbea336
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98e58ec9966d0e0534d078fc5741f267bf02e735
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974341"
---
# <a name="unable-to-create-binding-configuration-element-for-editing"></a>No se puede crear el elemento de configuración del enlace para su edición
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| Versión del producto |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                      |
|    Identificador del evento     |                                                                  0                                                                   |
|  Origen del evento   |                                                                  0                                                                   |
|    Componente    |                                                                  0                                                                   |
|  Nombre simbólico  |                                                                  0                                                                   |
|  Texto del mensaje   | No se puede crear el elemento de configuración del enlace para su edición. Compruebe los valores de las propiedades BindingType y BindingConfiguration. |
  
## <a name="explanation"></a>Explicación  
 Se produjo un error al cargar un elemento de enlace para visualizarlo en la interfaz de usuario. Este error se produce con frecuencia con los enlaces personalizados. Probablemente falta el elemento de enlace en el archivo de configuración y, por lo tanto, no está disponible en la lista desplegable para el enlace.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe los valores de la **BindingType** y **BindingConfiguration** propiedades.  
  
 Para obtener más información sobre la creación de elementos de configuración de enlace, vea el recurso siguiente:  
  
-   [Configuración del adaptador de WCF-NetMsmq](../core/configuring-the-wcf-netmsmq-adapter.md)