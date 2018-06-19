---
title: Trasvase de registros | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- log shipping
ms.assetid: 25bc9724-1c99-43d0-8cd1-3ed8eaa60268
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd90e23fc99988bb134a77befe3195ca507037d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262116"
---
# <a name="log-shipping"></a>Trasvase de registros
El envío de registros proporciona funciones de servidor en espera, en ocasiones denominadas copia de seguridad semiactiva, que reduce el tiempo de inactividad en caso de error del sistema.  
  
 A causa del diseño distribuido de la base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], al realizar copias de seguridad, es preciso asegurarse de proporcionar un punto coherente en el que estas copias puedan restaurarse. Las transacciones pueden abarcar varias bases de datos; si una de éstas se queda sin conexión y debe restaurarse, todas las bases de datos relacionadas tendrán que restaurarse en un solo punto temporal para asegurar que el sistema se encuentre en un estado en el que se garantice su coherencia. Algunas bases de datos no participan en las transacciones distribuidas. Para obtener más información, consulte [copia de seguridad y restaurar las bases de datos de BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md).  
  
 El trabajo de copia de seguridad de BizTalk Server marcas de registro de Microsoft SQL Server para proporcionar un proceso automático que produce conjuntos de copias de seguridad de bases de datos. Estos conjuntos de copias de seguridad incluyen puntos sincronizados que se utilizan durante el proceso de restauración. Como parte del proceso de restauración de un conjunto de bases de datos producidas por el trabajo de copia de seguridad de BizTalk Server, el último archivo de copia de seguridad de registro para cada una de las bases de datos se restaura en una marca de registro específica mediante la penúltima marca. Con ello, es posible restaurar las bases de datos a un estado coherente y reducir de forma significativa la cantidad de datos perdidos. Se debería utilizar la penúltima marca de registro. Aunque SQL Server incluye una característica de envío de registros, se debería utilizar únicamente la característica de envío de registros de BizTalk Server al realizar una copia de seguridad de las bases de datos de BizTalk Server y al efectuar su restauración.  
  
> [!NOTE]
>  El modelo de recuperación simple del servidor SQL Server no es compatible con las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ya que el modelo de recuperación simple no realiza ninguna copia de seguridad del registro de transacciones y, por lo tanto, no mantiene un registro de la actividad desde la copia de seguridad más reciente.  Configure el servidor SQL Server para usar el modelo de recuperación completa y garantizar la integridad de los datos en los conjuntos de copias de seguridad de bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Información avanzada sobre la copia de seguridad y restauración](../core/advanced-information-about-backup-and-restore1.md)