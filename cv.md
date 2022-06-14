### **rsschool-cv**
---
# **Veronika Djioeva**
**********************************************************
DOB: 4 January 1983  

POB: Tbilisi, Georgia  

#### _Contact Info:_ 
----------------------------------------------------------
9 M.Dadiani-Anchabadze str; Tbilisi, GE  

Mobile: + (995 595) 030 407  

[Discord:](https://discord.com/) @Veronika_J#1267 

Email: v.jioeva@gmail.com    

***
***
### Briefly About Me
10 + years’ experience in banking sector. Business Analyst with over 5 years of experience supporting business solution software and analyzing business operations. Aiming to utilize my strong prioritization skills and analytical ability to achieve the goals of company.  
  > I want to change working sphere, so I have started learning Front-End Development.  
  
  ***
  ***
# Skills
***
- T-SQL;
- Microsoft Server Management Studio;
- Visual Reporting Studio 2005/2008;
- ✨HTML5; CSS; Bootstrap; 
***
## _Code Example:_

```
DECLARE @ContractTypeid INT, @ContractNumber VARCHAR(30)

DECLARE Curs CURSOR FOR

SELECT c.ContractNumber, acp1.ContractTypeID FROM Contracts c
JOIN AccountContractProducts acp1 ON acp1.AccountContractProductId = c.AccountContractProductId
JOIN ContractTypes ct ON ct.ContractTypeID = acp1.ContractTypeID
WHERE ct.SystemContractTypeID=1 AND c.ContractStatusId=2 AND c.ContractDate<'20210401'

OPEN Curs
FETCH NEXT FROM Curs INTO @ContractNumber, @ContractTypeid
WHILE @@FETCH_STATUS=0

BEGIN 

DECLARE @DisbursementConditionTypeId INT
DECLARE Internal CURSOR FOR 

SELECT cdct.DisbursementConditionTypeId FROM Cls_DisbursementConditionTypes cdct
WHERE cdct.DescrLocal IN ('Inerest rate type', 'Temporary interest rate type 1',
'Temporary interest rate type 2') AND cdct.ContractTypeId=@ContractTypeid

OPEN Internal
FETCH NEXT FROM Internal INTO @DisbursementConditionTypeId
WHILE @@FETCH_STATUS=0

BEGIN 
IF NOT EXISTS (SELECT 1 FROM DisbursementConditions dc  WHERE dc.LoanApplicationId=@ContractNumber
AND dc.DisbursementConditionTypeId=@DisbursementConditionTypeId )

INSERT INTO DisbursementConditions
(
  LoanApplicationId,
  DisbursementConditionTypeId
)
SELECT
  @ContractNumber,
  @DisbursementConditionTypeId

FETCH NEXT FROM Internal INTO @DisbursementConditionTypeId

END

CLOSE Internal
DEALLOCATE Internal

FETCH NEXT FROM Curs INTO @ContractNumber, @ContractTypeid

END 
CLOSE Curs
DEALLOCATE Curs  

```  

# Work Experience
---
#### *2014 - to present ProCredit Bank, Georgia*
> Department: Service Support Group  
>
> Position – Service Support Group Specialist  

#### *2012- 2014 ProCredit Bank, Georgia*
> Department: IT Department, Application Support Unit  
>
> Position: Application Support Specialist  

#### *2010- 2012 ProCredit Bank, Georgia*
> Project: Migration to New Core Banking Software  
>
> Position: Specialist  

#### *2008- 2010 ProCredit Bank, Georgia*
> Department: Credit Methodology Department  
>
> Position: Credit Methodology Specialist  

#### *2004-2006 AIR BOOK OFFICE LTD “TRANSAVIA”*
> Position: Manager  

# Personal Qualifications
---
- Excellent problem solving and deductive reasoning skills;
- Ability to listen, see the big picture and resolve conflicts;
- Excellent organizational ability with a high attention to detail;
- Capacity to make decisions and think on my feet;
- Ability to work independently and as a team player;
# Certifications
---
- Database Development - Delta Learning July 2012
- International Accounting Standards – Accounting and Audit Training Center March 2006
# Languages 
---

- Russian - Native
- Georgian - Native
- English - B1
- Spanish - Basic

