---
title: Lotes de mensajes transaccionales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1790c05-e3f7-4667-8a9e-f6f208e55e40
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28be423aa500ba8950b5b2100ce68dba7743bd79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279532"
---
# <a name="transactional-message-batches"></a>Lotes de mensajes transaccionales
Algunos adaptadores deben coordinar una transacción externa con un interno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] transacciones. Por ejemplo, el adaptador de SQL proporcionado con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe coordinar una [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] transacción con un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] transacciones. Para ello, el adaptador necesita tener acceso a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] un objeto de transacción. Un objeto de transacción explícitamente se crea y asociado al lote antes de que el lote se envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Un lote que tiene asociado un objeto de transacción recibe el nombre de lote transaccional. Si se suministra su propio objeto de transacción del Coordinador de transacciones distribuidas de Microsoft (MSDTC), puede lograr el "garantiza que, una vez y sólo una vez", la entrega de datos dentro y fuera de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Los adaptadores de bases de datos transaccionales, como el adaptador de SQL, tienen la posibilidad de interbloqueos en la base de datos externa, debido a que solo se usa una transacción para el lote. Este es el motivo por el que el tamaño del lote del adaptador de SQL se codifica en uno.  
  
 Si el adaptador debe dar de alta los administradores de recursos adicionales, por ejemplo, otra base de datos o MSMQ, en el ámbito de dicha transacción, es necesario crear y pasar al motor de mensajería, así como explicitar una transacción externa. La creación de una transacción externa y su asociación a un lote recibe el nombre de lote transaccional. Un adaptador transaccional es un adaptador que hace uso de los lotes transaccionales mediante la creación expresa de una transacción externa del Coordinador de transacciones distribuidas de Microsoft (MSDTC).  
  
 Uno de los motivos proporciona un adaptador [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con una transacción consiste en asegurarse de que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o el sistema externo tenga un registro de los datos. Este registro garantiza que el mensaje se entrega una única vez.  
  
> [!NOTE]
>  Para obtener más información acerca de MSDTC, vea la documentación para el Coordinador de transacciones distribuidas en: [http://go.microsoft.com/fwlink/?LinkId=44297](http://go.microsoft.com/fwlink/?LinkId=44297).  
  
 El adaptador de archivo es un ejemplo de un adaptador que no necesita obtener acceso a la transacción, porque las operaciones del archivo externo que administra no son transaccionales. En este caso, el adaptador no proporciona un objeto de transacción a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Por otro lado, el adaptador de SQL interactúa con una base de datos SQL y puede tener operaciones adicionales fuera de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] interacciones de mensajes. Una transacción MSDTC externa en este caso puede tener sentido para el adaptador pasar a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Controlar transacciones](../core/handling-transactions.md)