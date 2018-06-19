---
title: Referencia de certificado ambigua | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7a6a60d-97e6-4c60-86be-83efb4a50f99
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 304ded9572ba6598f7f2132a678a14b2b3301c10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230708"
---
# <a name="ambiguous-certificate-reference"></a>Referencia de certificado ambigua
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Referencia de certificado ambigua; se ha encontrado más de un certificado válido.|  
  
## <a name="explanation"></a>Explicación  
 Se ha encontrado más de un certificado válido.  
  
#### <a name="user-action"></a>Acción del usuario  
 Comprobar solo un certificado válido configurado.  
  
## <a name="verify-certificate"></a>Comprobar el certificado 
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.  
  
9. Haga clic en **Editar**.  
  
10. En el **Editor de identidad** diálogo cuadro, asegúrese de que los criterios de búsqueda en el **referencia de certificado** sección está configurada correctamente para indicar únicamente un certificado en el certificado **almacén nombre**.  
  
## <a name="verify-a-certificate-for-the-wcf-custom-and-the-wcf-customisolated-adapters"></a>Comprobar que un certificado de WCF-Custom y los adaptadores de WCF-CustomIsolated  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **comportamiento** ficha.  
  
9. Asegúrese de los criterios de búsqueda en el **referencia de certificado** sección está configurada correctamente para indicar únicamente un certificado en el certificado **nombre del almacén**.  
  
10. En el complemento Certificado, asegúrese de que únicamente esté instalado un certificado para los criterios de búsqueda que configuró para el transporte WCF.  
  
## <a name="see-also"></a>Vea también
[Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)  
 