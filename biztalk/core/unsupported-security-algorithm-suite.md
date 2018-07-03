---
title: Conjunto de algoritmos de seguridad no admitida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11696fed-c3a8-4b11-8249-9f99f7abc8f2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32b00fea76b95a76cbb6b88f18056bba798e1381
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990989"
---
# <a name="unsupported-security-algorithm-suite"></a>Conjunto de algoritmos de seguridad no compatible
## <a name="details"></a>Detalles  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                     Conjunto de algoritmos de seguridad no compatible: {0}                      |

## <a name="explanation"></a>Explicación  
 Este error se produce cuando la propiedad del conjunto de algoritmos de seguridad de una ubicación de recepción o un puerto de envío se establece en un valor incorrecto.  

## <a name="user-action"></a>Acción del usuario  
 Asegúrese de que la propiedad de protocolo de transacción está establecida en un valor válido.  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  

2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  

3. Busque la aplicación y, a continuación, busque su transporte.  

4. Haga clic con el botón secundario en el nombre del transporte.  

5. Haga clic en **Propiedades**.  

6. En el puerto **tipo** lista, seleccione **WCF-NetTcp**.  

7. Haga clic en **configurar**.  

8. En el **propiedades de transporte WCF-NetTcp** cuadro de diálogo, haga clic en el **seguridad** ficha.  

9. En el **la seguridad de mensaje** sección, asegúrese de que los valores de **algorithmsuite** son correctos.
