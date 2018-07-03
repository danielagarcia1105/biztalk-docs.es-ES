---
title: Esquema de dirección no válida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b059289-654e-40d6-a092-2a685e6e10f7
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c9a0e7a9c200d2efc7d0e6e81158379200d55af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981005"
---
# <a name="invalid-address-scheme"></a>Esquema de dirección no válido
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                        000                                         |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                  Esquema de dirección no válida. se esperaba "{0}" esquema.                   |
  
## <a name="explanation"></a>Explicación  
 Ha proporcionado un esquema de protocolo que no coincide con el tipo definido por el enlace de transporte.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.  
  
2. En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3. Busque la aplicación y, a continuación, busque su transporte.  
  
4. Haga clic con el botón secundario en el nombre del transporte.  
  
5. Haga clic en **Propiedades**.  
  
6. En el puerto **tipo** lista, seleccione el puerto correcto.  
  
7. Haga clic en **configurar**.  
  
8. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.  
  
9. En el **dirección (URI)** texto, asegúrese de que el valor de dirección coincide con el tipo del adaptador WCF que se está usando.  
  
   Además, si usa el adaptador WCF-Custom con un tipo de enlace proporcionado por el sistema, compruebe el valor de la **tipo de enlace** lista el **enlace** ficha. Si el **tipo de enlace** está configurado para **customBinding**, la dirección debe coincidir con el elemento de enlace de transporte que aparecen en la **tipo de enlace** lista en el **Enlace** ficha.