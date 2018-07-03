---
title: Se encontró el certificado no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b3a9ae8-a9d7-4025-bacd-443e136ff980
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a069ee0c934f9a7636646a07bd5a7f777d88c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020588"
---
# <a name="invalid-certificate-found"></a>Se encontró un certificado no válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                             Se encontró un certificado no válido.                              |
  
## <a name="explanation"></a>Explicación  
 No proporcionó un certificado válido para un transporte WCF.  

#### <a name="user-action"></a>Acción del usuario
Agregar un certificado. 
  
## <a name="add-a-certificate"></a>Agregar un certificado  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3. Busque la aplicación y, a continuación, busque su transporte.  
  
4. Haga clic con el botón secundario en el nombre del transporte.  
  
5. Haga clic en **Propiedades**.  
  
6. En el puerto **tipo** lista, seleccione el puerto correcto.  
  
7. Haga clic en **configurar**.  
  
8. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.  
  
9. Haga clic en **Editar**.  
  
10. En el **Editor de identidad** diálogo cuadro, asegúrese de que los criterios de búsqueda en el **referencia de certificado** sección está configurada correctamente para indicar certificados válidos.  
  
    Personalizada de WCF y los adaptadores de WCF-CustomIsolated, asegúrese de que los criterios de búsqueda en el **referencia de certificado** sección está configurada correctamente para indicar un certificado válido en el certificado **nombre Store** .  
  
## <a name="add-a-certificate-for-standard-wcf-adapters"></a>Agregar un certificado para adaptadores de WCF  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3. Busque la aplicación y, a continuación, busque su transporte.  
  
4. Haga clic con el botón secundario en el nombre del transporte.  
  
5. Haga clic en **Propiedades**.  
  
6. En el puerto **tipo** lista, seleccione el puerto correcto.  
  
7. Haga clic en **configurar**.  
  
8. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **seguridad** ficha.  
  
9. Asegúrese de que el **huella digital** propiedades para los certificados de servicio y cliente indiquen certificados válidos en el certificado **nombre Store**.  
  
   En el complemento Certificado, asegúrese de que están instalados certificados válidos para el transporte WCF.  
  
## <a name="see-also"></a>Vea también 
  
[Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)  