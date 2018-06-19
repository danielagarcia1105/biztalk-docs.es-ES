---
title: Cómo hacer copia de seguridad la configuración del servidor de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f89050-c204-4d44-a875-299e690489ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad54aba8f8f49adeb8534bdbe28add15f0fe9638
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247660"
---
# <a name="how-to-back-up-the-biztalk-server-configuration"></a>Cómo efectuar una copia de seguridad de la configuración de BizTalk Server
Como parte de la creación de una copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se debe realizar una copia de este tipo de los valores de configuración asociados con el equipo en el que se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En el caso de que se produzca un error de hardware que requiera la sustitución del equipo, el proceso de restauración se simplifica considerablemente si se dispone de una copia del archivo de configuración original.  
  
 El Administrador de configuración de BizTalk Server crea un archivo XML en el que se almacenan los valores de configuración de cada uno de los equipos en los que se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Siempre que se cambie la configuración de los servidores BizTalk Server, se debe exportar el archivo de configuración a la ubicación de copia de seguridad correspondiente. Con esto, se contribuye a garantizar que el archivo de configuración se encuentre disponible en el caso de que resulte necesario reemplazar el servidor BizTalk Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-back-up-the-biztalk-server-configuration"></a>Para efectuar una copia de seguridad de la configuración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft BizTalk Server**y, a continuación, haga clic en **configuración de BizTalk Server**.  
  
2.  En **configuración de Microsoft BizTalk Server**, haga clic en **Exportar configuración**.  
  
3.  En el **Guardar como** cuadro de diálogo, vaya a la ubicación donde se almacenan las copias de seguridad.  
  
4.  En el **nombre de archivo** , escriba un nombre para el archivo de configuración y, a continuación, haga clic en **guardar**.  
  
## <a name="see-also"></a>Vea también  
 [Realizar una copia de seguridad de un equipo que ejecuta BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md)   
 [Cómo recuperar la configuración de BizTalk Server](../core/how-to-recover-the-biztalk-server-configuration.md)