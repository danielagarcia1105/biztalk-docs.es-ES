---
title: Proceso de implementación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying
- deploying, SSO
- LogonExternalUser test [SSO]
- security, SSO
- SSO, LogonExternalUser test
- SSO, security
ms.assetid: 7dd4c022-c70b-467a-bf94-dc4ac6029f81
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21be32ec58c90c1fb95134a002bee82ef5d78fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240668"
---
# <a name="deployment-process"></a>Proceso de implementación
Los pasos siguientes ofrecen información general de alto nivel de una implementación segura de inicio de sesión único empresarial. Para conocer los procedimientos detallados que se deben realizar en SQL Server, vea la documentación de SQL Server.  
  
1.  En el controlador de dominio de SQL Server, utilice el Asistente para nueva confianza para crear una confianza con las siguientes propiedades:  
  
    -   **Nombre:** ORCH.com  
  
    -   **Dirección:** bidireccional  
  
    -   **Lados:** sólo este dominio  
  
    -   **Nivel de autenticación de confianza - dominio Local de salida:** autenticación selectiva  
  
    -   **Contraseña:** elija una contraseña  
  
    -   **Confirmar confianza de salida:** sí  
  
    -   **Confirmar confianza de entrada:** n  
  
2.  En el controlador de dominio ORCH.com, utilice el Asistente para nueva confianza para crear una confianza con las siguientes propiedades:  
  
    -   **Nombre:** SQL.com  
  
    -   **Dirección:** bidireccional  
  
    -   **Lados:** sólo este dominio  
  
    -   **Nivel de autenticación de confianza - dominio Local de salida:** autenticación selectiva  
  
    -   **Contraseña:** debe ser la misma que para ORCH.com  
  
    -   **Confirmar confianza de salida:** sí  
  
    -   **Confirmar confianza de entrada:** n  
  
3.  En el controlador de dominio ORCH.com, establezca la confianza de ámbito de dominio para la entrada de SQL.COM.  
  
4.  En el controlador de dominio SQL.com, establezca la confianza de ámbito de dominio para la salida de ORCH.COM.  
  
5.  En el controlador de dominio ORCH.com, eleve el nivel funcional del dominio a Windows Server 2003 SP2 o Windows 2008 R2.  
  
6.  En el dominio ORCH, cree los siguientes usuarios nuevos:  
  
    -   ORCH\SSOSvcUser  
  
    -   ORCH\TestAppUser  
  
    -   ORCH\AffAppUser  
  
7.  Agregar **actuar como parte del sistema operativo** a SSOSvcUser y TestAppUser.  
  
8.  Agregar **puedan autenticar** privilegios a ORCH\TestAdmin.  
  
9. Agregue ORCH\SSOSvcUser a SQL2 en el dominio SQL. Este paso requiere el uso de la Vista avanzada en MMC Active Directory.  
  
10. En el equipo SQL2, cree estos dos inicios de sesión nuevos:  
  
    -   ORCH\TestAdmin  
  
    -   ORCH\SSOSvcUser  
  
11. En el dominio SQL2, cree dos grupos globales de dominio:  
  
    -   ORCH\SSOAdminGroup  
  
    -   ORCH\SSOAffAdminGroup  
  
12. Agregar **puedan autenticar** privilegio al grupo ORCH\SSOAdminGroup.  
  
13. En la base de datos SQL2, cree el siguiente inicio de sesión:  
  
    -   ORCH\SSOAdminGroup  
  
14. Instale el servidor secreto principal del siguiente modo:  
  
    -   Inicie sesión en NTS5 con ORCH\TestAdmin.  
  
    -   Instale ESSO usando SQL2 como servidor secreto principal.  
  
15. Inicie sesión en HIS1 con ORCH\TestAdmin e instale el inicio de sesión único empresarial. Configure ESSO como SSO unido a HIS2 con el nombre de servidor de base de datos SQL2.  
  
16. Instale la utilidad de administración de inicio de sesión único empresarial en HIS3 con ORCH\TestAdmin.  
  
17. Agregue los siguientes usuarios a los grupos siguientes:  
  
    -   Agregue ORCH\TestAppUser a ORCH\SSOAdminGroup  
  
    -   Agregue ORCH\AffAppUser a ORCH\TestAffUserGroup  
  
18. Instale SQL Server Enterprise Edition en HIS3 y agregue el inicio de sesión ORCH\AffAppUser.  
  
19. En el equipo HIS1, abra el símbolo del sistema y use los siguientes comandos para establecer delegación restringida y transición de protocolo:  
  
    -   **setspn - A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**  
  
    -   **setspn - A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**  
  
20. En el **ORCH\SSOSvcUser** y **ORCH\TestAppUser** páginas de propiedades, establezca la delegación apropiada para ambas cuentas de usuario seleccionando las opciones siguientes:  
  
    -   **Confiar en este usuario para la delegación sólo a servicios especificados**  
  
    -   **Usar cualquier protocolo de autenticación**  
  
21. Usando ORCH\TestAdmin en el equipo HIS1, realice lo siguiente:  
  
    -   Agregue ORCH\TestAppUser al grupo Usuarios de escritorio remoto  
  
    -   GRANT **suplantar una vez autenticado** privilegios a ORCH\SSOSvcUser  
  
    -   GRANT **suplantar una vez autenticado** privilegios a ORCH\TestAppUser  
  
22. Para comprobar la implementación, inicie sesión en HIS1 como ORCH\TestAppUser y ejecute la siguiente configuración de aplicación:  
  
     Ejecutar prueba LogonExternalUser.  
  
    ```  
    <SSO>  
       <application name="TestApp">  
          <description>An SSO Test Affiliate Application</description>  
          <contact>AffAppUser@ESSOV2.EBiz.Com</contact>  
          <appUserAccount>ORCH\TestAffAdminGroup</appUserAccount>  
          <appAdminAccount>ORCH\TestAffUserGroup</appAdminAccount>  
          <field ordinal="0" label="User ID" masked="no" />  
          <field ordinal="1" label="Password" masked="yes" />  
          <flags   
             groupApp="no"   
             configStoreApp="no"   
             allowTickets="no"   
             validateTickets="yes"   
             allowLocalGroups="yes"   
             ticketTimeout="yes"   
             adminGroupSame="no"   
             enableApp="yes"   
             hostInitiatedSSO="yes"   
             validatePassword="yes"/>  
       </application>  
    </SSO>  
  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Información general de la implementación de SSO](../core/sso-deployment-overview.md)