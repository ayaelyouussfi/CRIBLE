# CRIBLE
CRIBLE
nt main() {
    int n;
    printf("Entrez un nombre : ");
    scanf("%d", &n);
    int prime[10000];  // tableau fixe, max 10 000
    for (int i = 0; i <= n; i++)
        prime[i] = 1;
    prime[0] = prime[1] = 0;
    for (int i = 2; i * i <= n; i++) {
        if (prime[i]) {
            for (int j = i * i; j <= n; j += i)
                prime[j] = 0;
        }
    }
    printf("Nombres premiers jusqu'a %d :\n", n);
    for (int i = 2; i <= n; i++)
        if (prime[i]) printf("%d ", i);
    return 0;
}

