# Ontology for Datafusion Systems Built on Neural Network

Note that the project is on the very early stage of development. In other words it is in progress and everything can be changed...

## Goals
The goals of the ontology is defined by the following competency questions:

1. What kind of components carries the given set of indicators?
2. What kind of project develops such components?

## Ontology Usage

Examples of DL-queries that can be used to answer the competency questions questions:

1. What kind of components carries the given set of indicators?
    * Example 1:
        ```
        Q: carries some Efficiency and carries some 'Computational Complexity'
        A: DMLP Component
        ```
    * Example 2:
        ```
        Q: carries some Efficiency and not (carries some 'Tested With Real World Data')
        A: CAPE Component, DMLP Component
        ```
2. What kind of project develops such components?
    * Example 1:
        ```
        Q: develops some (carries some Efficiency and carries some 'Computational Complexity')
        A: DMLP
        ```

## Ontology Extention Method

To exend the onotlogy it is necessary:

1. Create three individuals: [project name], [project name]-component, [project name]-refence
2. Refine project individual:
   * Make the individual to be an individual of class `Project`
   * Make the individual to be an individual of class `'is applied to' some [here some subclass of 'Application Area' should be used]`
   * Link the individual through the property `'has component'` with the corresponding component individual
   * Link the individual through the property `'has reference'` with the corresponding reference individual
3. Refine component individual:
   * Make the individual to be an individual of classes `carries some [here some subclass of 'DF Indicator' should be used]`. To link multiple expression use `and`; to state that the component does not carry an indicator use `not`
   * Make the individual to be an individual of classes `implements some [here some subclass of 'Neural Network' should be used]`
4. Refine refence individual:
   * Link the individual through the property `'has citation'` with the citation string
   * Link the individual through the property `'has link'` with the link on the project