Link to Github Repository:
<a href="https://github.com/FelixBrett/Final-Report" class="uri">https://github.com/FelixBrett/Final-Report</a>

This project seeks to prove that being Black, whether African or
Caribbean, makes an individual in the Understanding Society dataset
significantly more likely to live in a single parent household. The
single parent advocacy group, Gingerbread, reports that Black and
minority ethnic people are more likely to live in single parent
households \[Rabindrakumar 2018:4\]. However it appears that all
ethnicities are somewhat less likely to live in single parent households
than White people with the small exception of ‘Other’ and the large
exception of Black people. The above table also displays much lower
single parenthood rates than those given by Gingerbread (22.7% as of
2018). This is because this study calculates single parenthood
exclusively based on the composition of households whereas the standard
definition includes children and young people who are in any way
dependent on their parents but don’t necessarilly live with them
\[Rabindrakumar 2018:3\].

Single-parenthood is a particularly interesting type of household
composition because it is traditionally indicative of hardship. People
living in single parent households are more likely to be disabled (both
parents and children); they’re more likely to report psychological
distress and in 2015, 20% of single parents lived in persistent poverty
compared to only around 5% of coupled parents \[Rabindrakumar 2018:10\].
The relationship between single parenthood rates and race is thus
important both because it can be very debilitating for families and
because it appears to impact some races significantly more than others.
In this report, I hypothesise that race is the most important
independent variable available for explaining single parenthood rates.
Hence I examine the effect of monthly pay on each race’s propensity to
be single parents as well as immigration status. These two variables
represent socio-economic conditions which vary significantly across
races and which could act as better independent variables for explaining
higher single parenthood rates in Black people (i.e that high single
parenthood rates in Black people are due to their low average monthly
pay or the fact that most are immigrants). However I hypothesised to
begin with that being Black is the best explanatory variable, because if
lower monthly pay or being an immigrant could explain higher single
parenthood rates than the other non-White ethnicities would follow Black
people and also display higher single parenthood rates compared to White
people.

It is important to clarify that because of the way the data is coded, my
assertion is that Black individuals are more likely than other races to
live in single parent households. As opposed to being that Black people
are more likely to be raised in single parent households or that Black
people are more likely to be single parents. This clarification is
important as I decided to use individual data rather than household
data. Household data doesn’t take into account the complexities made
possible by the existence of multi-ethnic households. It would be
inaccurate to label the entire household with the ethnicity of only one
of the household’s members. Therefore my project began by subsetting
each individual in to a type of household and a race so that each race’s
propensity to live in a certain type of household could be calculated.
However a major problem occured in that ethnicities with a tendency to
have more children then appeared to have higher single-parenthood rates,
because children and young people in single parent households would then
act to increase the single parenthood rate.

To solve this problem I’ve had to remove all households where not all
members of the family are of the same race. This is a huge limitation
because it means that the growing significance of multi-ethnic
households is being ignored. But it is necessary to ensure that race is
the independent variable in the study.

I began the project by mutating the data so that ethnicities are clearly
labelled and the household types are simplified into groups. This
simplicity also means that the different kinds of household match
typical British social units such as the single-parent household and the
nuclear family. The household types are:

1 = 1 adult

2 = 1 adult with 1+ children (who I will refer to as single parent
households)

3 = 2 adults and no children

4 = 2 adults and 1+ children

5 = 3+ adults and no children

6 = 3+ adults and children

The household types were going to be labelled (respectively) : lives
alone, single parent, couple with no children, couple with children,
cohabiting adults and cohabiting adults with children but then I
realised that the dataset doesn’t actually verify the type of family.
For example, two adults living together with children aren’t
necessarilly a couple and they therefore don’t necessarilly constitute a
nuclear family. Whereas a group of cohabiting adults could actually be a
married couple living with their adult children. Therefore some groups
of adults living together may actually constitute a nuclear family.
After establishing the different household types, race was tabulated
against household type. This was done with the aid of a package called
crosstab which helped in producing a simple tabulation of the survey
data.

    ##                            household_type      1      2      3      4      5      6    Sum
    ## race                                                                                      
    ## White_British                              17.57   4.15  33.29  21.47  15.86   7.66 100.00
    ## Irish                                      22.34   4.62  25.19  22.93  15.15   9.76 100.00
    ## Indian                                      6.47   2.33  15.44  31.41  23.17  21.17 100.00
    ## Pakistani                                   3.88   3.93   5.69  37.01  14.08  35.41 100.00
    ## Bangladeshi                                 2.90   3.34   3.51  38.66  12.48  39.10 100.00
    ## Chinese                                    17.79   1.51  22.40  28.78  24.92   4.61 100.00
    ## Black_Caribbean                            26.33  14.04  12.49  14.90  19.71  12.54 100.00
    ## Black_African                              12.72  15.32   6.34  30.31  16.89  18.42 100.00
    ## Any_other_white_background                 13.84   4.32  24.80  35.78  14.14   7.11 100.00
    ## Other                                      13.87   7.93  14.11  31.10  17.17  15.83 100.00

Looking at the column marked ‘2’ we can see that Black people (both
African and Caribbean) are significantly more likely to be single
parents than the other ethnic groups. There are other salient
differences between the ethnicities, such as that Bangladeshi people are
both the most likely to live in very large families and the least likely
to live alone. This project explores the first finding, because there
are a lot of different ways in which 3+ adults and 1+ children can live
together, thus we can’t label this household type as any particular kind
of family. Whereas we can deduce that the vast majority of households
with 1 adult and 1+ children are a single parent with their child or
children. Cases wherein the child isn’t actually related to the adult
taking care of them will also reflect the same socio-economic conditions
as if they were related and thus this will still be treated as a
single-parent households.

But before examining the other variables beside race, it’s important to
check whether high single parenthood rates in Black people are
consistent throughout the waves of the dataset or whether there are
anomalies.

![](Explore-how-the-household-composition-varies-across-ethnic-groups-in-Britain_files/figure-markdown_strict/4-1.png)

This graph demonstrates both that the pattern of single-parenthood rates
in Black-Caribbean and Black-African people are consistently higher than
for the other races in this survey and that Black-African people and
Black-Caribbean people are very similar in their single-parenthood rate.
The graph also shows Black people have been trending towards the other
ethnicities in recent waves.

Black-Caribbean people and Black-African people are near identical in
the rates. For this reason the data is then amalgamated so that
Black-Caribbean and Black-African people are the same value, Black.
Though it is interesting that Black-Africans and Black-Caribbeans are so
similar in single-parenthood rates when Black-Africans are much more
likely to be first generation immigrants to the UK than Black-Caribbean
people, as is shown in the table below. This is a substantial
socio-economic difference between Africans and Caribbeans as well as a
similarity between Africans and the other ethnicities.

    ##                            ukborn uk_born born_abroad    Sum
    ## race                                                        
    ## White_British                       97.58        2.42 100.00
    ## Irish                               63.75       36.25 100.00
    ## Indian                              29.55       70.45 100.00
    ## Pakistani                           37.91       62.09 100.00
    ## Bangladeshi                         27.68       72.32 100.00
    ## Chinese                             15.41       84.59 100.00
    ## Black_Caribbean                     48.77       51.23 100.00
    ## Black_African                       13.48       86.52 100.00
    ## Any_other_white_background          10.72       89.28 100.00
    ## Other                               36.34       63.66 100.00

After noticing this substantial difference within the Black population,
I wanted to explore the relationship between immigration status and
likelihood to live in a single-parent household. This is a particularly
interesting relationship to establish because there’s little research on
this correlation in Britain, despite the fact that single parenthood is
reported to be more common in Black and Minority Ethnic people
\[Rabindrakumar 2018:4\]. Hence if single parenthood is believed to be
more common in minorities, it could easily be the same case for
immigrants. However, I hypothesise that immigration status has no
substantial impact on the single parenthood rate because if being an
immigrant made a person significantly more or less likely to live in a
single parent household, then this would be reflected in a difference
between African and Caribbean people.

Below are two bar charts examining the proportion of people who live in
each household type depending on their immigration status. It must be
noted however that the sample size of these graph is very limited
compared to the previous graph because the dataset only contains
information on immigration status for the first wave of the dataset
(wave a).

![](Explore-how-the-household-composition-varies-across-ethnic-groups-in-Britain_files/figure-markdown_strict/6-1.png)![](Explore-how-the-household-composition-varies-across-ethnic-groups-in-Britain_files/figure-markdown_strict/6-2.png)

The first graph shows that in the dataset which includes all
ethnicities, immigrants and native born individuals are equally likely
to live in single parent households. The second graph then shows that UK
born Black people are significantly more likely to live in single parent
households than Black immigrants. These graphs seem to verify my
hypothesis that immigration status doesn’t effect the likelihood of a
person to live in a single parent household. However the case appears
different among Black people, possibly because immigrants are more
likely to live in traditional family structures with 2+ adults per
house. It could be the case that both among Black people and everyone
else, being an immigrant entails different socio-economic conditions,
some of which are amenable to single parenthood and others not.

![](Explore-how-the-household-composition-varies-across-ethnic-groups-in-Britain_files/figure-markdown_strict/7-1.png)![](Explore-how-the-household-composition-varies-across-ethnic-groups-in-Britain_files/figure-markdown_strict/7-2.png)

These graphs show that we cannot say that Black people are more likely
to live in single parent households because they have a lower income.
While Black-Caribbean and Black-African people are the 4th and 3rd
lowest paid ethnicities in the dataset respectively, they’re monthly pay
isn’t very different from Indian, Other, White-British and Irish people.

The total lack of correlation may be due to the fact that poverty in
single parent households is and only can be measured after expenses as
opposed to by monthly pay. Hence a correlation may exist between
household wealth and the single parenthood rate but not between monthly
pay and the single parenthood rate. Wealth probably would have a close
correlation with the single parenthood rate as people who live in single
parent households have less disposable wealth than single people and
people who live in larger families. But to point out that single parents
are on average poorer after paying their expenses due to their reliance
on a single adults income would be quite redundant. This, essay is about
examining the causes of single parenthood not its effects. Furthermore,
the lack of a negative correlation between the single parenthood rate
and monthly pay is a positive indication that both single parents and
young people who live in single parent households have similar access to
decent paying jobs as people who don’t live in single parent households.
Gingerbread concur that the current record levels of employment in
single parents is encouraging \[Rabindrakumar 2018:6\] and that the next
target for Government should be to help single parents struggling with
in-work povety. But we can conclude that low pay is not a cause of
single parenthood.

Ultimately, this essay has proved beyond reasonable doubt that Black
people are significantly over represented among British people who live
in single parent households. The finding that Black people born in the
UK are more likely to live in single parent households is particularly
important as it disproves any assertion that Black single parenthood is
the result of a poor adaptation to life in Britain. This essay presents
an impetus for policy makers to do more to support single parents. I
want to reiterate again that there is no inherent problem with being a
single parent or being raised by one, but the facts suggest that single
parent families are significantly worse off than their peers. This essay
therefore presents an impetus for policy makers to do more to support
single parents. Particularly as the socio-economic distress which
plagues single parent households disproportionately harms people due to
their race.
