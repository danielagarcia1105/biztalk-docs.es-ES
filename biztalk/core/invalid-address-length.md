---
title: Longitud de dirección no válida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e16eb6-e77e-4361-ac91-0730004c4433
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8da5e041ad861557817491695f0d7972a207864a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008477"
---
# <a name="invalid-address-length"></a>Longitud de dirección no válida
## <a name="details"></a>Detalles  

|                 |                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------|
|  Nombre del producto   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
| Versión del producto |                 [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                  |
|    Identificador del evento     |                                              0                                              |
|  Origen del evento   |                                              0                                              |
|    Componente    |                                              0                                              |
|  Nombre simbólico  |                                              0                                              |
|  Texto del mensaje   | Longitud de dirección no válida; Especifica la longitud de la dirección es {0} límite es de caracteres, {1} caracteres adicionales. |

## <a name="explanation"></a>Explicación  
 Proporcionó una dirección que excede de la longitud máxima de 255 caracteres para un transporte WCF. Este límite lo impone BizTalk Server, no WCF.  

## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar una dirección válida.  

#### <a name="to-configure-a-valid-address"></a>Para configurar una dirección válida  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.  

2. En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.  

3. Busque la aplicación y, a continuación, busque su transporte.  

4. Haga clic con el botón secundario en el nombre del transporte.  

5. Haga clic en **Propiedades**.  

6. En el puerto **tipo** lista, seleccione el puerto correcto.  

7. Haga clic en **configurar**.  

8. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.  

9. En el **dirección (URI)** texto, asegúrese de que la dirección no supera la longitud máxima de 255 caracteres.
