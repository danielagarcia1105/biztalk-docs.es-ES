---
title: Servidor secreto principal | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, about Master Secret server
- Master Secret server, SSO
- SSO, encryption key
- Master Secret server, encryption key
- SSO, Master Secret server
ms.assetid: 93685a19-6c27-45db-bfc1-957574362687
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d02d5608546e86801bfc4a2281c42f902594e79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="master-secret-server"></a>Servidor secreto principal
El servidor secreto principal es el servidor de inicio de sesión único empresarial (SSO) que almacena el secreto principal (clave de cifrado). Este servidor genera el secreto principal cuando lo solicita un administrador de SSO y lo almacena cifrado en el Registro. Sólo los administradores de inicio de sesión único pueden obtener acceso al secreto principal.  
  
 Los demás servidores de inicio de sesión único comprueban cada 30 segundos si ha cambiado el secreto principal. Si ha cambiado, lo leen de forma protegida; de lo contrario, continúan usando el secreto principal que tienen almacenado en la memoria caché. El servicio SSO utiliza el secreto principal para cifrar y descifrar las credenciales de usuario.  
  
 No puede usar el sistema SSO hasta que un administrador de SSO configure el servidor secreto principal y genere el secreto principal. El servidor secreto principal genera el secreto principal durante la configuración. Sólo los administradores de SSO pueden generar el secreto principal. Un administrador de SSO debe configurar el servidor secreto principal y la base de datos de SSO para que las aplicaciones puedan usar el servicio SSO.  
  
> [!IMPORTANT]
>  Tras generar el secreto principal, se recomienda encarecidamente realizar una copia de seguridad y almacenarla en un lugar seguro.  
  
 Cuando un administrador de SSO tiene que generar el secreto principal (por ejemplo, si el administrador de SSO desea cambiar el secreto principal periódicamente), el servidor secreto principal almacena tanto el secreto principal antiguo como el nuevo. El servidor secreto principal pasa después por todas las asignaciones, las descifra con el secreto principal antiguo y las vuelve a cifrar con el secreto principal nuevo.  
  
 Si el servidor secreto principal da error, todas las operaciones de tiempo de ejecución que se estén ejecutando continuarán haciéndolo, pero los servidores de SSO no podrán cifrar credenciales nuevas.  
  
> [!IMPORTANT]
>  Sólo puede haber un servidor secreto principal en el sistema SSO. Por tanto, se recomienda encarecidamente agrupar el servidor secreto principal. Para obtener más información, consulte [cómo agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md).  
  
## <a name="see-also"></a>Vea también  
 [Uso de SSO](../core/using-sso.md)