#!/usr/bin/perl -w
hanoi($ARGV[0],"A","B","C");

sub hanoi {
    my ($num,$org,$buf,$des) = @_;
    #print "num = $num\n";
    if($num eq "1") {
        print "move $org to $des\n";
        return 0;
    }
    else {
        $num--;
        hanoi($num,$org,$des,$buf);
        print "move $org to $des\n";
        hanoi($num,$buf,$org,$des);
    }
}
