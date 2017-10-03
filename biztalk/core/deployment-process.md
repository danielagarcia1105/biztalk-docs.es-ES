---
title: "Proceso de implementación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, deploying
- deploying, SSO
- LogonExternalUser test [SSO]
- security, SSO
- SSO, LogonExternalUser test
- SSO, security
ms.assetid: 7dd4c022-c70b-467a-bf94-dc4ac6029f81
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21be32ec58c90c1fb95134a002bee82ef5d78fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-process"></a><span data-ttu-id="d058b-102">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="d058b-102">Deployment Process</span></span>
<span data-ttu-id="d058b-103">Los pasos siguientes ofrecen información general de alto nivel de una implementación segura de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d058b-103">The following steps give a high-level overview of secure deployment of Enterprise Single Sign-On.</span></span> <span data-ttu-id="d058b-104">Para conocer los procedimientos detallados que se deben realizar en SQL Server, vea la documentación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d058b-104">For detailed procedures on the actions to take in SQL Server, see your SQL Server documentation.</span></span>  
  
1.  <span data-ttu-id="d058b-105">En el controlador de dominio de SQL Server, utilice el Asistente para nueva confianza para crear una confianza con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d058b-105">On the SQL Server domain controller, use the New Trust Wizard to create a trust with the following properties:</span></span>  
  
    -   <span data-ttu-id="d058b-106">**Nombre:** ORCH.com</span><span class="sxs-lookup"><span data-stu-id="d058b-106">**Name:** ORCH.com</span></span>  
  
    -   <span data-ttu-id="d058b-107">**Dirección:** bidireccional</span><span class="sxs-lookup"><span data-stu-id="d058b-107">**Direction:** Two-way</span></span>  
  
    -   <span data-ttu-id="d058b-108">**Lados:** sólo este dominio</span><span class="sxs-lookup"><span data-stu-id="d058b-108">**Sides:** This domain only</span></span>  
  
    -   <span data-ttu-id="d058b-109">**Nivel de autenticación de confianza - dominio Local de salida:** autenticación selectiva</span><span class="sxs-lookup"><span data-stu-id="d058b-109">**Outgoing Trust Authentication Level - Local Domain:** Selective authentication</span></span>  
  
    -   <span data-ttu-id="d058b-110">**Contraseña:** elija una contraseña</span><span class="sxs-lookup"><span data-stu-id="d058b-110">**Password:** Choose a password</span></span>  
  
    -   <span data-ttu-id="d058b-111">**Confirmar confianza de salida:** sí</span><span class="sxs-lookup"><span data-stu-id="d058b-111">**Confirm Outgoing Trust:** Yes</span></span>  
  
    -   <span data-ttu-id="d058b-112">**Confirmar confianza de entrada:** n</span><span class="sxs-lookup"><span data-stu-id="d058b-112">**Confirm Incoming Trust:** No</span></span>  
  
2.  <span data-ttu-id="d058b-113">En el controlador de dominio ORCH.com, utilice el Asistente para nueva confianza para crear una confianza con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d058b-113">On the ORCH.com domain controller, use the New Trust Wizard to create a trust with the following properties:</span></span>  
  
    -   <span data-ttu-id="d058b-114">**Nombre:** SQL.com</span><span class="sxs-lookup"><span data-stu-id="d058b-114">**Name:** SQL.com</span></span>  
  
    -   <span data-ttu-id="d058b-115">**Dirección:** bidireccional</span><span class="sxs-lookup"><span data-stu-id="d058b-115">**Direction:** Two-way</span></span>  
  
    -   <span data-ttu-id="d058b-116">**Lados:** sólo este dominio</span><span class="sxs-lookup"><span data-stu-id="d058b-116">**Sides:** This domain only</span></span>  
  
    -   <span data-ttu-id="d058b-117">**Nivel de autenticación de confianza - dominio Local de salida:** autenticación selectiva</span><span class="sxs-lookup"><span data-stu-id="d058b-117">**Outgoing Trust Authentication Level - Local Domain:** Selective authentication</span></span>  
  
    -   <span data-ttu-id="d058b-118">**Contraseña:** debe ser la misma que para ORCH.com</span><span class="sxs-lookup"><span data-stu-id="d058b-118">**Password:** Must be the same as password for ORCH.com</span></span>  
  
    -   <span data-ttu-id="d058b-119">**Confirmar confianza de salida:** sí</span><span class="sxs-lookup"><span data-stu-id="d058b-119">**Confirm Outgoing Trust:** Yes</span></span>  
  
    -   <span data-ttu-id="d058b-120">**Confirmar confianza de entrada:** n</span><span class="sxs-lookup"><span data-stu-id="d058b-120">**Confirm Incoming Trust:** No</span></span>  
  
3.  <span data-ttu-id="d058b-121">En el controlador de dominio ORCH.com, establezca la confianza de ámbito de dominio para la entrada de SQL.COM.</span><span class="sxs-lookup"><span data-stu-id="d058b-121">On the ORCH.com domain controller, set the domain wide trust for Incoming from SQL.COM.</span></span>  
  
4.  <span data-ttu-id="d058b-122">En el controlador de dominio SQL.com, establezca la confianza de ámbito de dominio para la salida de ORCH.COM.</span><span class="sxs-lookup"><span data-stu-id="d058b-122">On the SQL.com domain controller, set the domain wide trust for Outgoing from ORCH.COM.</span></span>  
  
5.  <span data-ttu-id="d058b-123">En el controlador de dominio ORCH.com, eleve el nivel funcional del dominio a Windows Server 2003 SP2 o Windows 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="d058b-123">On the ORCH.com domain controller, raise the domain functional level to Windows Server 2008 SP2 or Windows Server 2008 R2.</span></span>  
  
6.  <span data-ttu-id="d058b-124">En el dominio ORCH, cree los siguientes usuarios nuevos:</span><span class="sxs-lookup"><span data-stu-id="d058b-124">In the ORCH domain, create the following new users:</span></span>  
  
    -   <span data-ttu-id="d058b-125">ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="d058b-125">ORCH\SSOSvcUser</span></span>  
  
    -   <span data-ttu-id="d058b-126">ORCH\TestAppUser</span><span class="sxs-lookup"><span data-stu-id="d058b-126">ORCH\TestAppUser</span></span>  
  
    -   <span data-ttu-id="d058b-127">ORCH\AffAppUser</span><span class="sxs-lookup"><span data-stu-id="d058b-127">ORCH\AffAppUser</span></span>  
  
7.  <span data-ttu-id="d058b-128">Agregar **actuar como parte del sistema operativo** a SSOSvcUser y TestAppUser.</span><span class="sxs-lookup"><span data-stu-id="d058b-128">Add **Act as part of the operating system** to SSOSvcUser and TestAppUser.</span></span>  
  
8.  <span data-ttu-id="d058b-129">Agregar **puedan autenticar** privilegios a ORCH\TestAdmin.</span><span class="sxs-lookup"><span data-stu-id="d058b-129">Add **Allowed to Authenticate** privilege to ORCH\TestAdmin.</span></span>  
  
9. <span data-ttu-id="d058b-130">Agregue ORCH\SSOSvcUser a SQL2 en el dominio SQL.</span><span class="sxs-lookup"><span data-stu-id="d058b-130">Add ORCH\SSOSvcUser to SQL2 in the SQL domain.</span></span> <span data-ttu-id="d058b-131">Este paso requiere el uso de la Vista avanzada en MMC Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d058b-131">(This step requires using Advanced View in Active Directory MMC.)</span></span>  
  
10. <span data-ttu-id="d058b-132">En el equipo SQL2, cree estos dos inicios de sesión nuevos:</span><span class="sxs-lookup"><span data-stu-id="d058b-132">On the SQL2 computer, create the following two new logins:</span></span>  
  
    -   <span data-ttu-id="d058b-133">ORCH\TestAdmin</span><span class="sxs-lookup"><span data-stu-id="d058b-133">ORCH\TestAdmin</span></span>  
  
    -   <span data-ttu-id="d058b-134">ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="d058b-134">ORCH\SSOSvcUser</span></span>  
  
11. <span data-ttu-id="d058b-135">En el dominio SQL2, cree dos grupos globales de dominio:</span><span class="sxs-lookup"><span data-stu-id="d058b-135">On the SQL2 domain, create two domain global groups:</span></span>  
  
    -   <span data-ttu-id="d058b-136">ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="d058b-136">ORCH\SSOAdminGroup</span></span>  
  
    -   <span data-ttu-id="d058b-137">ORCH\SSOAffAdminGroup</span><span class="sxs-lookup"><span data-stu-id="d058b-137">ORCH\SSOAffAdminGroup</span></span>  
  
12. <span data-ttu-id="d058b-138">Agregar **puedan autenticar** privilegio al grupo ORCH\SSOAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="d058b-138">Add **Allowed to Authenticate** privilege to the ORCH\SSOAdminGroup group.</span></span>  
  
13. <span data-ttu-id="d058b-139">En la base de datos SQL2, cree el siguiente inicio de sesión:</span><span class="sxs-lookup"><span data-stu-id="d058b-139">On the SQL2 database, create the following new login:</span></span>  
  
    -   <span data-ttu-id="d058b-140">ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="d058b-140">ORCH\SSOAdminGroup</span></span>  
  
14. <span data-ttu-id="d058b-141">Instale el servidor secreto principal del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="d058b-141">Install the Master Secret Server as follows:</span></span>  
  
    -   <span data-ttu-id="d058b-142">Inicie sesión en NTS5 con ORCH\TestAdmin.</span><span class="sxs-lookup"><span data-stu-id="d058b-142">Log on to NTS5 using ORCH\TestAdmin.</span></span>  
  
    -   <span data-ttu-id="d058b-143">Instale ESSO usando SQL2 como servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="d058b-143">Install ESSO, using SQL2 as the Master Secret Server.</span></span>  
  
15. <span data-ttu-id="d058b-144">Inicie sesión en HIS1 con ORCH\TestAdmin e instale el inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d058b-144">Log onto HIS1 using ORCH\TestAdmin, and install Enterprise Single Sign-On.</span></span> <span data-ttu-id="d058b-145">Configure ESSO como SSO unido a HIS2 con el nombre de servidor de base de datos SQL2.</span><span class="sxs-lookup"><span data-stu-id="d058b-145">Configure ESSO as SSO join HIS2, using database server name SQL2.</span></span>  
  
16. <span data-ttu-id="d058b-146">Instale la utilidad de administración de inicio de sesión único empresarial en HIS3 con ORCH\TestAdmin.</span><span class="sxs-lookup"><span data-stu-id="d058b-146">Install the Enterprise Single Sign-On Admin utility on HIS3 using ORCH\TestAdmin.</span></span>  
  
17. <span data-ttu-id="d058b-147">Agregue los siguientes usuarios a los grupos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d058b-147">Add the following users to the following groups:</span></span>  
  
    -   <span data-ttu-id="d058b-148">Agregue ORCH\TestAppUser a ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="d058b-148">Add ORCH\TestAppUser to ORCH\SSOAdminGroup</span></span>  
  
    -   <span data-ttu-id="d058b-149">Agregue ORCH\AffAppUser a ORCH\TestAffUserGroup</span><span class="sxs-lookup"><span data-stu-id="d058b-149">Add ORCH\AffAppUser to ORCH\TestAffUserGroup</span></span>  
  
18. <span data-ttu-id="d058b-150">Instale SQL Server Enterprise Edition en HIS3 y agregue el inicio de sesión ORCH\AffAppUser.</span><span class="sxs-lookup"><span data-stu-id="d058b-150">Install SQL Server Enterprise Edition on HIS3, and add login ORCH\AffAppUser.</span></span>  
  
19. <span data-ttu-id="d058b-151">En el equipo HIS1, abra el símbolo del sistema y use los siguientes comandos para establecer delegación restringida y transición de protocolo:</span><span class="sxs-lookup"><span data-stu-id="d058b-151">On the HIS1 computer, open a command prompt and use the following commands to set constrain delegation and protocol transition:</span></span>  
  
    -   <span data-ttu-id="d058b-152">**setspn - A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**</span><span class="sxs-lookup"><span data-stu-id="d058b-152">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**</span></span>  
  
    -   <span data-ttu-id="d058b-153">**setspn - A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**</span><span class="sxs-lookup"><span data-stu-id="d058b-153">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**</span></span>  
  
20. <span data-ttu-id="d058b-154">En el **ORCH\SSOSvcUser** y **ORCH\TestAppUser** páginas de propiedades, establezca la delegación apropiada para ambas cuentas de usuario seleccionando las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d058b-154">On the **ORCH\SSOSvcUser** and **ORCH\TestAppUser** property pages, set the proper delegation for both user accounts by selecting the following options:</span></span>  
  
    -   <span data-ttu-id="d058b-155">**Confiar en este usuario para la delegación sólo a servicios especificados**</span><span class="sxs-lookup"><span data-stu-id="d058b-155">**Trust this user for delegation to specified services only**</span></span>  
  
    -   <span data-ttu-id="d058b-156">**Usar cualquier protocolo de autenticación**</span><span class="sxs-lookup"><span data-stu-id="d058b-156">**Use any authentication protocol**</span></span>  
  
21. <span data-ttu-id="d058b-157">Usando ORCH\TestAdmin en el equipo HIS1, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d058b-157">Using ORCH\TestAdmin on the HIS1 computer, perform the following:</span></span>  
  
    -   <span data-ttu-id="d058b-158">Agregue ORCH\TestAppUser al grupo Usuarios de escritorio remoto</span><span class="sxs-lookup"><span data-stu-id="d058b-158">Add ORCH\TestAppUser to Remote Desktop User Group</span></span>  
  
    -   <span data-ttu-id="d058b-159">GRANT **suplantar una vez autenticado** privilegios a ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="d058b-159">Grant **Impersonate after authenticated** privilege to ORCH\SSOSvcUser</span></span>  
  
    -   <span data-ttu-id="d058b-160">GRANT **suplantar una vez autenticado** privilegios a ORCH\TestAppUser</span><span class="sxs-lookup"><span data-stu-id="d058b-160">Grant **Impersonate after authenticated** privilege to ORCH\TestAppUser</span></span>  
  
22. <span data-ttu-id="d058b-161">Para comprobar la implementación, inicie sesión en HIS1 como ORCH\TestAppUser y ejecute la siguiente configuración de aplicación:</span><span class="sxs-lookup"><span data-stu-id="d058b-161">Verify your deployment by logging onto HIS1 using ORCH\TestAppUser and running the following application configuration:</span></span>  
  
     <span data-ttu-id="d058b-162">Ejecutar prueba LogonExternalUser.</span><span class="sxs-lookup"><span data-stu-id="d058b-162">Run LogonExternalUser Test.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d058b-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="d058b-163">See Also</span></span>  
 [<span data-ttu-id="d058b-164">Información general de la implementación de SSO</span><span class="sxs-lookup"><span data-stu-id="d058b-164">SSO Deployment Overview</span></span>](../core/sso-deployment-overview.md)