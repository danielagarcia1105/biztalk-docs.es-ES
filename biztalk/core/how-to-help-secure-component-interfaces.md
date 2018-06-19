---
title: Cómo ayudar a componente seguro Interfaces | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, helping to secure
- security, component interfaces
ms.assetid: 03b2af44-78e7-4fdc-bfa3-7697b2a60986
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54136aaeae9578ae4e438c5bd8b95b902d618f96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255220"
---
# <a name="how-to-help-secure-component-interfaces"></a>Cómo proteger las interfaces de componentes
Antes de que pueda probar una interfaz de componente, debe establecer la seguridad para ésta. El siguiente procedimiento describe cómo configurar la seguridad de interfaz de componentes para la versión 8.4 de PeopleSoft pero puede utilizar le procedimiento para la versión 8.1.  
  
### <a name="to-configure-interface-security"></a>Para configurar la seguridad de interfaz  
  
1.  Expanda **PeopleTools**, expanda **seguridad**, expanda **perfiles de usuario**y, a continuación, expanda **permisos y Roles**.  
  
     ![](../core/media/psadapter-47-ps-configsecurity1.gif "PSAdapter_47_PS_ConfigSecurity1")  
  
2.  Haga clic en **las listas de permisos**.  
  
3.  Haga clic en **Buscar**.  
  
     ![](../core/media/psadapter-48-ps-configsecurity2.gif "PSAdapter_48_PS_ConfigSecurity2")  
  
4.  En el **búsqueda de listas de permiso** panel, seleccione la lista de los permisos pertinentes.  
  
     Aparecerá la siguiente ventana.  
  
     ![](../core/media/psadapter-49-ps-configsecurity3.gif "PSAdapter_49_PS_ConfigSecurity3")  
  
5.  Haga clic en la flecha derecha junto a la **tiempos de inicio de sesión** pestaña para visualizar más fichas.  
  
     ![](../core/media/psadapter-50-ps-configsecurity4.gif "PSAdapter_50_PS_ConfigSecurity4")  
  
6.  Haga clic en el **Interfaces de componentes** ficha.  
  
7.  Haga clic en el + (más) de inicio de sesión para agregar una nueva fila a la **Interfaces de componentes** lista.  
  
     Aparecerá un campo en el que puede escribir el nombre de la interfaz de componente.  
  
     ![](../core/media/psadapter-51-ps-configsecurity5.gif "PSAdapter_51_PS_ConfigSecurity5")  
  
8.  Escriba el nombre de la interfaz de componente y, a continuación, haga clic en **editar**.  
  
     Este ejemplo usa la interfaz de componente AR_ITEM_AGENT.  
  
     ![](../core/media/psadapter-52-ps-configsecurity6.gif "PSAdapter_52_PS_ConfigSecurity6")  
  
9. En la lista, seleccione el nivel de acceso deseado para cada método y, a continuación, haga clic en **Aceptar**.  
  
     Aparecerá la siguiente ventana.  
  
     ![](../core/media/psadapter-53-ps-configsecurity7.gif "PSAdapter_53_PS_ConfigSecurity7")  
  
10. Desplácese hacia abajo en el panel derecho y haga clic en **guardar**.  
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md)   
 [Apéndice C: usar Interfaces de componentes](../core/appendix-c-using-component-interfaces.md)