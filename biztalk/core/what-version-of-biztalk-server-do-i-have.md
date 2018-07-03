---
title: ¿Qué versión de BizTalk Server tengo? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb651202-f682-4e5f-8a79-221877af20a7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7003f2d3c61345462ca484f627110a6e507e748
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976981"
---
# <a name="what-version-of-biztalk-server-do-i-have"></a>¿Qué versión de BizTalk Server tengo?
Puede que esté ejecutando diferentes versiones y ediciones diferentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Este tema muestra cómo determinar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] información sobre la instalación, incluida la ruta de instalación, edición y número de versión.  

## <a name="use-the-registry"></a>Use el registro

1. Seleccione **iniciar**, tipo `regedt32`y, a continuación, vuelva a abrirlo.  

2. Expanda **HKEY_LOCAL_MACHINE**, expanda **SOFTWARE**, expanda **Microsoft**, expanda **BizTalk Server**y, a continuación, seleccione **3.0**.  

3. El panel de la derecha muestra la información de instalación, por ejemplo:  


   |      Subclave       |                                                                                                         Descripción                                                                                                          |
   |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  **InstallPath**   |                                             Indica la ruta de instalación en que se instaló [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].                                              |
   | **Productedition no válido** |                                                        Indica la edición, por ejemplo:<br /><br /> -Para desarrolladores<br />-Rama<br />-Estándar<br />-Enterprise                                                         |
   | **ProductVersion** | Indica la versión base del producto. Para la versión específica del producto, incluidos los service packs y actualizaciones acumulativas, consulte [versiones BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx). |

## <a name="use-the-control-panel"></a>Utilice el panel de control

1.  Seleccione **iniciar**, tipo `Programs and Features`y, a continuación, vuelva a abrirlo.  

2. En la lista, seleccione **Microsoft BizTalk Server**. Se muestran la versión y edición.

Consulte [versiones BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).

## <a name="see-also"></a>Vea también  
 [Introducción](../core/getting-started-with-biztalk-server.md)