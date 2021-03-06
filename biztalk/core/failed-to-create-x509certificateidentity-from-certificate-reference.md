---
title: No se pudo crear X509CertificateIdentity a partir de la referencia de certificado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3acee8e-c035-4e58-8bfc-397885b4d185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b991f9acb2b5cc193d24d36e1a5de8650e7af72b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988933"
---
# <a name="failed-to-create-x509certificateidentity-from-certificate-reference"></a>No se pudo crear X509CertificateIdentity a partir de la referencia de certificado
## <a name="details"></a>Detalles  

|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| Versión del producto |                                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                         |
|    Identificador del evento     |                                                                     0                                                                      |
|  Origen del evento   |                                                                     0                                                                      |
|    Componente    |                                                                     0                                                                      |
|  Nombre simbólico  |                                                                     0                                                                      |
|  Texto del mensaje   | No se pudo crear X509CertificateIdentity a partir de la referencia de certificado. (StoreName ={0}, StoreLocation ={1}, X509FindType ={2}, FindValue = "{3}") |

## <a name="explanation"></a>Explicación  
 Este error indica que el adaptador no pudo crear el X509Certificate especificado en la configuración de identidad de extremo.  

## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para comprobar las opciones de referencia de certificado.  

#### <a name="to-configure-the-certificate-reference-settings"></a>Para configurar las opciones de referencia de certificado  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  

2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  

3. Busque la aplicación y, a continuación, busque su transporte.  

4. Haga clic con el botón secundario en el nombre del transporte.  

5. Haga clic en **Propiedades**.  

6. En el puerto **tipo** lista, seleccione el puerto correcto.  

7. Haga clic en **configurar**.  

8. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.  

9. En el **identidad de extremo** sección, haga clic en **editar.**  

10. En el **Editor de identidad** diálogo cuadro, asegúrese de que el **referencia de certificado** configuración es válida.
