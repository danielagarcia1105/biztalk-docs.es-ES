---
title: "Cómo restaurar el almacén de certificados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c6f7551-d119-4668-9b52-6013f69a0302
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaeee6b762cf5af15ca7cba34864abd86682d4df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-restore-the-certificate-store"></a>Cómo restaurar el almacén de certificados
Como parte de la recuperación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es preciso restaurar el almacén de certificados. Si se efectúa la recuperación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, será necesario usar este procedimiento para restaurar el almacén de certificados. No se tendrá que llevar a cabo este procedimiento para recuperar el resto de las ediciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ya que el proceso de recuperación restaura el almacén de certificados automáticamente.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.  
  
### <a name="to-restore-the-certificate-store-biztalk-server-standard-edition"></a>Para restaurar el almacén de certificados (BizTalk Server Standard Edition)  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**y, a continuación, haga clic en **Internet Explorer**.  
  
2.  En el **herramientas** menú, haga clic en **opciones de Internet**.  
  
3.  En el **opciones de Internet** cuadro de diálogo, haga clic en el **contenido** ficha y, a continuación, haga clic en **certificados**.  
  
4.  En el **certificados** cuadro de diálogo, haga clic en el **otras personas** ficha y, a continuación, haga clic en **importación**.  
  
5.  En el **Asistente para importar certificados**, haga clic en **cancelar**.  
  
     Esto crea la **AddressBook** subárbol en el registro.  
  
6.  En el **certificados** cuadro de diálogo, haga clic en **cerrar**.  
  
7.  En el **opciones de Internet** cuadro de diálogo, haga clic en **Aceptar**.  
  
8.  Haga clic en **archivo**y, a continuación, haga clic en **cerrar** para salir de Internet Explorer.  
  
9. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit**y, a continuación, haga clic en **Aceptar**.  
  
10. En el Editor del Registro, desplácese hasta la siguiente clave del Registro:  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**  
  
11. Compruebe que la **AddressBook** hive está presente.  
  
## <a name="see-also"></a>Vea también  
 [Recuperar un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)