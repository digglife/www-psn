# NAME

WWW::PSN - Perl Module for fetching PSN profile and trophy data.

# VERSION

version 0.02

# SYNOPSIS

    use WWW::PSN;
    my $profile = profile('hajimuc'); # replace hajimuc with your PSN ID.
    print "Current Level: $profile->{'curLevel'}\n";

    # print all the titles
    my $detailed_trophies = trophies('hajimuc');
    for my $t ( @{$detailed_trophies->{list}} ) {
        print encode('utf-8',$t->{title}), "\n";
    }

# DESCRIPTION

`WWW::PSN` is Perl Module for fetching PSN profile and trophy data.

# METHODS

## profile($psn\_id)

User profile including overall trophy progress and numbers.

    {
       "isPlusUser" : "1",
       "curLevel" : "4",
       "handle" : "hajimuc",
       "progress" : "90",
       "avatarUrl" : "//static-resource.np.community.playstation.net/avatar_m/WWS_J/J0003_m.png",
       "trophies" : {
          "bronze" : "98",
          "silver" : "15",
          "gold" : "4",
          "platinum" : "0"
       },
       "totalLevel" : ""
    }

## trophies($psn\_id)

Detailed trophies data.

    {
       "overallprogress" : "90",
       "isPlusUser" : "1",
       "avatarUrl" : "//static-resource.np.community.playstation.net/avatar_m/WWS_J/J0003_m.png",
       "handle" : "hajimuc",
       "curLevel" : "4",
       "totalResults" : "15",
       "list" : [
          {
             "title" : "Far Cry® Primal",
             "imgUrl" : "//trophy01.np.community.playstation.net/trophy/np/NPWR09687_00_0090890723F98AD458C3F4EC288C1888A48F880D21/08B0C827B453E9D45ED0DCBE0CB6FFA59BFFD53E.PNG",
             "progress" : 85,
             "platform" : "ps4",
             "gameId" : "NPWR09687_00",
             "trophies" : {
                "silver" : 9,
                "bronze" : 30,
                "gold" : 2,
                "platinum" : 0
             }
          }
        ]
    }

# AUTHOR

Zhu Sheng Li <zshengli@cpan.org>

# COPYRIGHT AND LICENSE

This software is Copyright (c) 2016 by Zhu Sheng Li.

This is free software, licensed under:

    The MIT (X11) License
