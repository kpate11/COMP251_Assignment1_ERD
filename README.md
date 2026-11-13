# Assignment 1 - Creating an ER Diagram for MPLSRenters.com
This assignment will meet each of the objectives below:
1. Translate business use cases for data into entity relationships

2. Determine appropriate entity structure for relational databases

3. Apply the correct terminology to a ER Model

4. Design an ER model

## Instructions
For this assignment, your task is to analyze the provided business description and identify the necessary business rules to create an ER diagram. These rules will encompass relationships, constraints, and data requirements.

You are required to compile a README.md file, which will detail each entity along with a brief description of its purpose and the data it collects. Additionally, identify the relationships between entities and note any assumptions or questions you may have for the client based on the business description. You will also decide the answers to your assumptions on behalf of the client.

After completing the README.md file, your next step is to construct an ER Diagram based on the identified relationships from the business description. This diagram should be created using a free web-based tool called 'draw.io.' You'll find the shapes needed for your ER diagram under the 'Entity Relation' tab. Instructions on how to operate draw.io can be found in the assignment resources section below. **DRAW.IO must be used as your ER diagram tool**

## Business Description
MPLSRenters.com is a website that allows prospective apartment renters to create a profile and have
high-end luxury apartments make offers to prospective renters.

1.  A property can have many high-end amenities associated with it. The amenities that are
associated with a property are preset amenities that can be added to a property.  Each amenity will have a name and description. 
 If properties have unique amenities that are not a part of the preset amenities, then those details will go into
the long description for each property. A property will contain information such as first and last name, email, phone, address, short and long description, longitude/latitude of property, and rent range (the lowest and highest amount you can expect to pay).
2. Prospective renters can add as many amenities to their profile as they deem necessary. The amenities will
be the same preset amenities that can be added to a property.  A renter will collect the same information a property would collect, but will also include a renter's decision date, the number of bedrooms and bathrooms, and the lower and max rent value they are willing to spend.  
3. Prospective renters can add as many properties to their profile as they desire. A prospective renter can exist in the system without having a property associated with a profile.
4. A property can have multiple property agents associated with a property. A property does not
have to be associated with a property agent to exist within the database. Property agents can
be activated and deactivated from the system based on whether or not payment for a monthly
package was made on time.
5. Both a profile and a property can receive a classification. There are only three pre-determined
classifications that can be associated with a profile or property. A profile is classified based on
the lower and upper range a prospective renter is looking to have for monthly rent. A
property is classified based on the select amenities, square footage, and lower/upper rent range. Each classification will contain a title, description, and a classification identifier (ex.  A high-luxury, B high - mid-luxury, or C luxury property)
6. A property agent can sign-up for one of three packages. All property agents must have an agent
package. An agent package determines how much access they will be granted to user profile
information.  An Agent package will contain a name, the package description, and an agent option selection (monthly payment package or yearly payment package)
7. Property agents are able to make multiple offers to those who have profiles in the system. A
profile can receive multiple offers from an agent. A profile can decline or entertain an offer.  An offer will contain information such as a description of the offer, the offer expiration date, and the property name for which the offer is being made.

## Submission Guidelines

For this assignment, you will submit 2 items to the repository that has been assigned to you.  The two items that you will need to submit are listed below: 
1. The README.MD file that identifies the various Entities and a brief description of the entity and possible attributes, relationships, and assumptions. 
   1. When identifying relationships be sure to bold and uppercase the entity name, underline the verb and make sure relationships are bi-directional. 
   2. When identifying assumptions, make sure to answer your assumption with either a Yes or No and make sure your response is properly reflected in the ER diagram.  
   3. You can override this README.MD file that contains the instructions or extend this README.MD file by listing your requirements below the Assignment Resources section.

2. The draw.io XML file that contains your ER Diagram.  You will also need to take a snippet of the ER Diagram and add it as an image in your README file.

Once you have completed both of the items above, you will need to submit the link to your repository for assignment 1 prior to the due date and time listed.  Make sure you receive an email confirmation notifying you that the assignment has been submitted.

### Rubric
| Criteria           | Description                             | Points |
| -------------------| --------------------------------------- | ------ |
|**Deliverable 1 - Write-up documented in README.md file**   | Write-up identifies the various entities with brief description (4pts) <br> Write-up identifies the various relationships that exist between the entities (6pt) <br> Write-up list assumptions that provides context for cardinality and entity strength (2 pts) <br> Write-up contains uppercase entity names, underlined verb and relationships are bi-directional (3 pts)  |   15   |
|**Deliverable 2 - Properly structured ER diagram** | All Entities identified in deliverable 1 are visually represented in Workbench ER diagram. (4pts) <br> Relationship strength is indicated by solid or dotted line (2pt) <br> Foreign keys and Primary keys are identified and correctly assigned (2 pts) <br> Each column name indicates null vs not null (2pt) <br> Image of ER diagram is depicted in README.MD file (2 pt) <br> Associative entities are identified and properly captures the relationship between the two entities(3 pts)   |   15   |
|           |        |**Total Points:   30**   |


## Assignment Resources
- [Mark-down Syntax Cheat Sheet](https://enterprise.github.com/downloads/en/markdown-cheatsheet.pdf)
- [Make a ReadMe file Web-based Editor](https://www.makeareadme.com/)
- [Draw.io Web-based diagramming tool](https://app.diagrams.net/)
- [Creating Entity Relationship Diagrams using Draw.io](https://www.youtube.com/watch?v=lAtCySGDD48)

# Assumptions
1. Can an amenity exist on its own without being attached to any property or renter?  
   1. Yes.
   2. Reason: We may want to have amenities in place before they are actually tied to any specific property or renter - for future buildings or ideas.
 
2. Can a classification exist in the system even if no property or renter is current assigned to it? 
   1. Yes.
   2. Reason: This allows us to pre-define various levels of categories before a property or renter matches those specific criteria.
  
3. Can a property have unique, custom amenities that are not part of the standard preset list? 
   1. No.
   2. Reason: Any unique or one-off amenity not found in preset list will be placed in the long_description field as mentioned in the business rules.


 
# RELATIONSHIPS
1. One **PROPERTY** can be <ins>associated</ins> with zero to many **PROPERTY_AMENITY** records, and each **PROPERTY_AMENITY** <ins>belongs</ins> to one and only one **PROPERTY** record.
2. One **AMENITY** can be <ins>associated</ins> with zero to many **PROPERTY_AMENITY** records, and each **PROPERTY_AMENITY** <ins>belongs</ins> to one and only one **AMENITY** record.
3. One **PROSPECTIVE_RENTER** can <ins>have</ins> zero to many **RENTER_AMENITY** records, and each **RENTER_AMENITY** <ins>belongs</ins> to one and only one **PROSPECTIVE_RENTER** record.
4. One **AMENITY** can be <ins>associated</ins> with zero to many **RENTER_AMENITY** records, and each **RENTER_AMENITY** <ins>belongs</ins> to one and only one **AMENITY** record. 
5. One **PROSPECTIVE_RENTER** can <ins>save</ins> zero to many **RENTER_PROPERTY** records, and each **RENTER_PROPERTY** <ins>belongs</ins> to one and only one **PROSPECTIVE_RENTER** record.
6. One **PROPERTY** can be <ins>saved</ins> by zero to many **RENTER_PROPERTY** records, and each **RENTER_PROPERTY** belongs to one and only one **PROPERTY** record.
7. One **PROPERTY** can be <ins>associated</ins> with zero to many **PROPERTY_AGENT** records, and each **PROPERTY_AGENT** <ins>belongs</ins> to one and only one **PROPERTY** record.
8. One **AGENT** can be <ins>associated</ins> with zero to many **PROPERTY_AGENT** records, and each **PROPERTY_AGENT** <ins>belongs</ins> to one and only one **AGENT** record. 
9. One **CLASSIFICATION** can be <ins>assigned</ins> to zero to many **PROPERTY** records, and each **PROPERTY** <ins>has</ins> one and only one **CLASSIFICATION** record.
10. One **CLASSIFICATION** can be <ins>assigned</ins> to zero to many **RENTER** records, and each **RENTER** <ins>has</ins> one and only one **CLASSIFICATION** record.
11. One **PACKAGE** can be <ins>assigned</ins> to one to many **AGENT** records, and each **AGENT** <ins>has</ins> one and only one **PACKAGE**.
12. One **AGENT** can <ins>make</ins> zero to many **OFFER** records, and each **OFFER** belongs to one and only one **AGENT.**
13. One **RENTER** can <ins>receive</ins> zero to many **OFFER** records, and each **OFFER** belongs to one and only one **RENTER.**


 
